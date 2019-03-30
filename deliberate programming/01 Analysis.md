# Analysis
Layouting text means taking an existing text, the original/source, and arrange its words in a new way in lines.

The building blocks of texts:

* Paragraph
  * Line
      * Word

Paragraphs have to be kept intact during layout. Lines will be newly created from words matching the stated line length. Word will be kept intact, except for words longer than the line length and words with hyphens in them.

Words are separated by single spaces in the destination text, even though they might be separated by several spaces in the source or even by a line break.