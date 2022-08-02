# Code Style Guide

## General

### Indentation

Indent 2 spaces. No tabs.

Use blank lines between blocks to improve readability. Indentation is two spaces. Whatever you do, don't use tabs. For existing files, stay faithful to the existing indentation.

### Line length

Maximum line length is 120 characters.

If the line is to long, add `\` and indent the rest of the line

## Pipelines

Pipelines should be split one per line if they don't all fit on one line. (Respect of the maximim line length)

If a pipeline all fits on one line, it should be on one line.

If not, it should be split at one pipe segment per line with the pipe on the newline and a 2 space indent for the next section of the pipe. This applies to a chain of commands combined using '|'
If the pipeline contain `&&` see "Syntax `[[ a = b ]] && c`" for more.

## Conditions

### General

Put `; then` and `; do` on the same line as `if`, `for` or `while`

#### Example

##### Bad

```shell
for a in "$@"
do
    local aname="${a%%[=]*}"
    local avalue="${a#*=}"
    local bname=${(q)aliases[$aname]}
    aname="${(q)aname}"
    if (( ${+opts[(r)-s]} ))
    then
      tmp=-s
      tmp="${(q)tmp}"
      quoted="$aname $bname $tmp"
    elif (( ${+opts[(r)-g]} ))
    then
      tmp=-g
      tmp="${(q)tmp}"
      quoted="$aname $bname $tmp"
    else
      quoted="$aname $bname"
    fi
    quoted="${(q)quoted}"
done
```

##### Good

```shell
for a in "$@"; do
    local aname="${a%%[=]*}"
    local avalue="${a#*=}"
    local bname=${(q)aliases[$aname]}
    aname="${(q)aname}"
    if (( ${+opts[(r)-s]} )); then
      tmp=-s
      tmp="${(q)tmp}"
      quoted="$aname $bname $tmp"
    elif (( ${+opts[(r)-g]} )); then
      tmp=-g
      tmp="${(q)tmp}"
      quoted="$aname $bname $tmp"
    else
      quoted="$aname $bname"
    fi
    quoted="${(q)quoted}"
done
```

### Syntax `[[ a = b ]] && c`

If the line respect the maximum length (120). You can use this syntax. Otherwise use a normal `if` instead

#### Example

##### Bad

```shell
is-at-least 5.3 && .zi-add-report "${ZI[CUR_USPL2]}" "Bindkey ${(j: :)${(q+)@}}" || .zi-add-report "${ZI[CUR_USPL2]}" "Bindkey ${(j: :)${(q)@}}"
```

##### Good

```shell
if is-at-least 5.3; then
  .zi-add-report "${ZI[CUR_USPL2]}" "Bindkey ${(j: :)${(q+)@}}"
else
  .zi-add-report "${ZI[CUR_USPL2]}" "Bindkey ${(j: :)${(q)@}}"
fi
```
