# Text Layouter
Write a program to do simple text layouting:

* text lines are created with a certain maximum length,
* text lines are aligned left, right, center, or as a block.

The program reads the text to be formatted from StdIn and produces the result on StdOut.

Example usage based on text sample below:

```
$ mobydick.txt > layout 40
Call me Ishmael. Some years ago — never
mind how long precisely — having little
or no money in my purse, and nothing
particular to interest me on shore, I
thought I would sail about a little and
see the watery part of the world. It is
a way I have of driving off the spleen
...
$
```

No line is longer than 40 characters as stated as the first parameter to the program. All lines are left aligned, which is the default (or could be specified with `left` as the last parameter).

Alternatively the text can be right aligned like this:

```
$ mobydick.txt > layout 40 right
 Call me Ishmael. Some years ago — never
 mind how long precisely — having little
    or no money in my purse, and nothing
   particular to interest me on shore, I
 thought I would sail about a little and
 see the watery part of the world. It is
  a way I have of driving off the spleen
...
$
```

Centered (`center`) alignment works the same, but blocking the the is different in that it inserts additional spaces where necessary:

```
$ mobydick.txt > layout 40 block
1234567890123456789012345678901234567890
Call  me Ishmael. Some years ago — never
mind how  long precisely — having little
or  no  money in my purse,  and  nothing
particular  to interest  me on  shore, I
thought I  would sail about a little and
see the watery  part of the world. It is
a  way I have of driving off  the spleen
...
$
```

The necessary spaces are distributed across all gaps between words to render the text in a balanced way.

### Special cases
#### Long words
Words itself longer than a line will be cut at the end and continue on the next line.

```
Word: abcdefghijklmnopq
Line length: 5

Resulting layout:

abcde
fghij
klmno
qp

```

#### Hyphened words
Words including a hyphen can be broken at the hypen it need be.

```
Word: object-orientation

Line length: 20
Resulting layout:

object-orientation

Line length: 10
Resulting layout:

object-
orientation

```

#### Paragraphs
Paragraphs are separated by a blank line and to be carried over to the layouted text.

```
Text without paragraphs:

Call me Ishmael. Some years ago — never
mind how long precisely — having
little or no money in my purse, and nothing
particular to interest me
on shore, I thought I would sail about a little and see the watery part
of the world.

Layout with line length of 40:

Call me Ishmael. Some years ago — never
mind how long precisely — having little
or no money in my purse, and nothing
particular to interest me on shore, I
thought I would sail about a little and
see the watery part of the world
```

```
Text with paragraphs:

Call me Ishmael.

Some years ago — never
mind how long precisely — having
little or no money in my purse, and nothing
particular to interest me
on shore, I thought I would sail about a little and see the watery part
of the world.

Layout with line length of 40:

Call me Ishmael.

Some years ago — never mind how long
precisely — having little or no money in
my purse, and nothing particular to
interest me on shore, I thought I
would sail about a little and see the
watery part of the world.
```

## Text sample
Source: ['Moby Dick' by Herman Melville at Project Gutenberg](http://www.gutenberg.org/files/2701/2701-0.txt)

> Call me Ishmael. Some years ago — never mind how long precisely — having
little or no money in my purse, and nothing particular to interest me
on shore, I thought I would sail about a little and see the watery part
of the world. It is a way I have of driving off the spleen and
regulating the circulation.

> Whenever I find myself growing grim about the mouth; whenever it is a damp, drizzly November in my soul; whenever I find myself involuntarily pausing before coffin warehouses, and bringing up the rear of every funeral I meet; and especially whenever my hypos get such an upper hand of me, that it requires a strong moral principle to prevent me from deliberately stepping into the street, and methodically knocking people’s hats off — then, I account it high time to
get to sea as soon as I can. This is my substitute for pistol and ball.

> With a philosophical flourish Cato throws himself upon his sword; I
quietly take to the ship. There is nothing surprising in this. If they
but knew it, almost all men in their degree, some time or other,
cherish very nearly the same feelings towards the ocean with me.