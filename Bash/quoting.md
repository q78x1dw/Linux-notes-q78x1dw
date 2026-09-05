# Quoting

## Escape
It preserves the literal value of the next character that follows, removing any special meaning it has(Exception : \newline == newline continuation)

## Single Quote
preserves the literal value of each character within the quotes. A single quote may not occur between single quotes,

## Double Quotes
 =`''` but with the exception of ‘$’, ‘`’, ‘\’ when history expansion is enabled, ‘!’.
The backslash retains its special meaning only when followed by one of the following characters: ‘$’, ‘`’, ‘"’, ‘\’, or newline

## ANSI-C Quoting

Character sequences of the form $'string' are treated as a special kind of single quotes. The sequence expands to string, with backslash-escaped characters in string replaced as specified by the ANSI C standard.



