# Questions

## What is pneumonoultramicroscopicsilicovolcanoconiosis?

The maximum length for a word.

## According to its man page, what does `getrusage` do?

This function reports resource usage totals for processes specified by processes,
storing the information in *rusage.
http://www.gnu.org/software/libc/manual/html_node/Resource-Usage.html

## Per that same man page, how many members are in a variable of type `struct rusage`?

16
http://www.gnu.org/software/libc/manual/html_node/Resource-Usage.html
## Why do you think we pass `before` and `after` by reference (instead of by value) to `calculate`,
## even though we're not changing their contents?

Because passing large structs by value takes up a lot of memory, and can be very slow.

## Explain as precisely as possible, in a paragraph or more, how `main` goes about reading words from a file. In other words,
## convince us that you indeed understand how that function's `for` loop works.

The for loop in 'main', will read over each character of the infile, using fgetc() until it reaches the end of the file.
From there it will check each character to make sure that it is either an alphabetical character, or an apostrophe,
if not it checks to see if its a number (if it is a number, it goes to the end of that 'word' and skips over it),
if that fails the final else/if checks for a whole word.  If we get to the final
else/if then we terminate the current word by adding a '\0' to the end.


## Why do you think we used `fgetc` to read each word's characters one at a time rather than use `fscanf` with a format string like
## `"%s"` to read whole words at a time? Put another way, what problems might arise by relying on `fscanf` alone?

fgetc will read char by char allowing you to run a check based on the char being alphabetical/apostrophe/numberic/etc.
fscanf will read until it reaches whitespace, so non-alphabetical chars could sneak through the check and cause problems.

## Why do you think we declared the parameters for `check` and `load` as `const` (which means "constant")?

Because they will not change.
