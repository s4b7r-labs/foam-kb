# bash

For some examples see [powercontrol-client](https://github.com/s4b7r/powercontrol-client/blob/main/reset-clienstate.sh).

## Process substitution

https://tldp.org/LDP/abs/html/process-sub.html

```bash
cat $(./command)
```

Can also return file descriptors for stdin and stdout with `>(COMMAND)` and `<(COMMAND)`.

## tee

Can use `tee` to "multiplex" streams, see e.g. https://unix.stackexchange.com/a/47514

https://www.man7.org/linux/man-pages/man1/tee.1.html

## Everything except X "wildcard"

```bash
rm !(dontdeletethis.md)
```

https://www.putorius.net/run-rm-command-but-exclude-one-file.html

## History synchronization with Television (`tv`)

### Symptom

On Aurora Linux, where the CLI "bling" setup can replace Bash's native `Ctrl-R` reverse search with Television's command-history picker, a newly executed command may already appear in Bash's `history` output while still being absent from the `Ctrl-R` picker.

### Cause

Bash has two relevant history states:

- the current shell's in-memory history;
- the persisted history file, usually `${HISTFILE:-${HOME}/.bash_history}`.

Bash's `history` builtin sees the current shell's in-memory history, while Television's built-in `bash-history` channel reads the history file directly. Bash normally writes recent commands to the history file when the shell exits. `histappend` prevents overwriting the file, but does not make Bash write every command immediately.

This distinction is useful beyond Television: any tool that inspects the history file independently of Bash can lag behind the current shell unless history is flushed explicitly.

### Minimal fix

After Aurora's shell setup has been sourced, append one complete command to the `PROMPT_COMMAND` array:

```bash
PROMPT_COMMAND+=('history -a')
```

`history -a` appends commands entered in the current shell to the history file whenever Bash displays the next prompt, so Television can see them.

### Synchronizing concurrent terminals

To also import commands appended by other open Bash sessions:

```bash
__sync_bash_history() {
    history -a
    history -n
}

if [[ ! " ${PROMPT_COMMAND[*]} " =~ " __sync_bash_history " ]]; then
    PROMPT_COMMAND+=(__sync_bash_history)
fi
```

Here:

- `history -a` persists commands from the current shell;
- `history -n` imports history lines added to the history file by other shells.

Open a fresh terminal after changing `.bashrc`. Repeatedly sourcing `.bashrc` can otherwise duplicate prompt hooks in the current shell.

### `PROMPT_COMMAND` array quoting pitfall

This is wrong:

```bash
PROMPT_COMMAND+=(history -a)
```

It creates two array elements. Bash then runs `history` and separately tries to execute `-a`.

Use:

```bash
PROMPT_COMMAND+=('history -a')
```

Quoting keeps `history -a` as one prompt command.
