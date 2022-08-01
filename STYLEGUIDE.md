# Code Style Guide

## General

### Indentation

Indent 2 spaces. No tabs.

Use blank lines between blocks to improve readability. Indentation is two spaces. Whatever you do, don't use tabs. For existing files, stay faithful to the existing indentation.

### Line length

Maximum line length is 80 characters. 

If the line is to long, add `\` and indent the rest of the line

## Pipelines

Pipelines should be split one per line if they don't all fit on one line. (Respect of the maximim line length)

If a pipeline all fits on one line, it should be on one line.

If not, it should be split at one pipe segment per line with the pipe on the newline and a 2 space indent for the next section of the pipe. This applies to a chain of commands combined using '|' 
If the pipeline contain `&&` see "Syntax `[[ a = b ]] && c`" for more.

## Conditions

### General

Put `; then` and `; do` on the same line as `if`, `for` or `while`

### Syntax `[[ a = b ]] && c`

This syntax should be avoided. Use a normal `if` instead

#### Example

##### Bad
``` shell
is-at-least 5.3 && .zi-add-report "${ZI[CUR_USPL2]}" "Bindkey ${(j: :)${(q+)@}}" || .zi-add-report "${ZI[CUR_USPL2]}" "Bindkey ${(j: :)${(q)@}}"
```

##### Good
``` shell
if is-at-least 5.3; then
  .zi-add-report "${ZI[CUR_USPL2]}" "Bindkey ${(j: :)${(q+)@}}"
else
  .zi-add-report "${ZI[CUR_USPL2]}" "Bindkey ${(j: :)${(q)@}}"
fi
```

## `eval`

Eval should be avoided if possible