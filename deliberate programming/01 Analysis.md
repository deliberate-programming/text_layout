# Analysis
Layouting text means taking an existing text, the original/source, and arrange its words in a new way in lines.

The building blocks of texts:

* Paragraph
  * Line
      * Word

Paragraphs have to be kept intact during layout. Lines will be newly created from words matching the stated line length. Word will be kept intact, except for words longer than the line length and words with hyphens in them.

```
-Source:

abc def-ghi
jklmnopq

abcd efghijklmn op-qrst

-Destination with line length 7:

abc def-
ghi
jklmnop
q

abcd
efghijk
lmn op-
qrst

```

Words are separated by single spaces in the destination text, even though they might be separated by several spaces in the source or even by a line break.

```
-Source:

abc  def    ghij
  kl
  
-Destination with line length 7:
abc def
ghij kl
```

Single spaces between words are used for left/right/centered alignment. But for block alignment there might be more spaces needed to spread the words apart so each line is of the required length.

```
-Source:

abc  def    ghij
  kl
  
-Destination with line length 10:
1234567890

-left alignment
abc def
ghij kl

-right alignment
   abc def
   ghij kl

-center alignment
 abc def
 ghij kl

-block alignment
abc    def
ghij kl
```

With block alignment the last line should not be filled up with spaces. That would not look nice.
