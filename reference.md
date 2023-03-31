# graph-markup-lang Language Reference

## Introduction

### Notation

Grammar is notated using a syntax similar to [EBNF](https://en.wikipedia.org/wiki/Extended_Backus%E2%80%93Naur_form). Example:

```py
STRING = UNQUOTED_STRING
       | QUOTED_STRING;
```

TODO: more

### Notes on Encoding

The specification does not place restrictions on the input encoding, as long as it can losslessly represent all 7-bit ASCII printable characters. For example, the most official parsers accept UTF-8, except for the C parser, which takes ASCII.

String literals are represented internally as UTF-8. If your encoding does not support UTF-8 literals, you can escape them using `\uXXXX` escape sequences.

## Tokens

### Comment

```py
COMMENT = "#[^\n]*";
```

### Whitespace

Whitespace has no semantic meaning in GML. It is only used to separate tokens. It should be discarded by the parser.

```py
WHITESPACE = "[\t\n\r\u000B\u000C \u0085\u200E\u200F\u2028\u2029]+";
```

Any one sequence of abitrary whitespace characters is treated the same from any other arbitrary sequence of whitespace.

### Literal Keywords

```py
KW_NULL = "null";
KW_TRUE = "true";
KW_FALSE = "false";
```

These keywords have special meanings when used as literals, so they are not interpreted as strings. You can represent the literal string by surrounding them in quotes.

For example:

```json
boolean: true;
string: "true";
```

### String Literals

```py
STRING = UNQUOTED_STRING
       | QUOTED_STRING;
```

String literals don't need to be placed between quotes if it contains only a small set of characters. If you need to represent arbitrary text, you need to surround it in quotes.

#### Unquoted String

TODO

#### Quoted String

TODO


