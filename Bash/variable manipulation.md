${#somevar} len(somevar)

The ${var:offset} and ${var:offset:length} constructs can be used to obtain a substring. Strings are zero-indexed. Both offset and length are arithmetic expressions.

There are three basic string replacement forms available: ${var#pattern}, ${var%pattern} and ${var/pattern/replacement}. The first two are used for deleting content from the start and end of a string respectively. The third is used to replace a match with different content.

$(( expression )) evaluate arithmetic expression