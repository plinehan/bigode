Uz,

Ok, so the main file is 'bigode.tex'.  It basically #includes all the other files,
and includes a bunch of danky TeX magic that you should ignore.

Each other chapter has a single '.tex' file.  These files are named after whatever
word caught my eye in the title of the chapter.

You maybe can start on "stirfry.tex", which is still in a very raw state.

Check out 'feijao.tex', which is done and has a lot of good examples.  The top part:

\mychapter
{chapter_corn.jpg}
{feij\~{a}o . arroz . mango salsa . picante}
{refried feij\~{a}o vermelho e arroz vermelho accompanied willfully by
mango salsa and the standard brasilian table hot}

is a macro thing i created... the first parameter is the graphic for this chapter,
the second is the short name for the chapter (this appears in the table of contents)
and the third is the long name for the chapter.

All of the chapters have had their "\mychapter" headers fixed.  I think they've
all had their footnotes escaped with "\footnote"s, but in the "undone" chapters
those footnotes need to be moved to be right next to the text they footnote.

In general, don't worry about the spacing of the layout in the output PDF.  Some of the
chapter titles are broken between two pages, and the spacing between sections
is too big, and the spacing between items in ingredients lists is too big.  We'll
fix this all in the end by fixing their macros.

'feijao.tex' has examples of basically everything... ingredient lists, steps to
follow (i called that macro 'algorithm'), sections, subsections, subsubsections,
footnotes, etc.

There are some parts where Ank inserts some eecummings-style poetry where I might
have to handle the formatting... TeX is just super bizarre.  If you see anything like
that, just insert the text "TODO" next to it.  We'll grep for TODOs later and fix
them up.

I made the ASCII layout nice and pretty, but we maybe shouldn't do that.  I think
thats part of why I got so hung up.

Important notes about LaTeX:

======================
Be careful about the '%' character.  It is the comment character in LaTeX.  I
think I correctly escaped ('\%') all percent signs, but I might not have.

Vertical spacing is important, and white space is largely ignored.  A blank line
means a paragraph break.  Two spaces between words are treated as one, so don't
worry about putting two spaces after the period or anything.

Ending a line with "\\" forces a line break, but you shouldn't need that. Probably
just mark those parts with TODOs.
======================

Oh, so you basically go through your paper copy to get what the formatting is,
and then add the correct markups to the tex file.  I already escaped all of the
accent marks and hats, but you'll need to look for italics in the paper copy and
mark them up like this: "\textit{this text is italic}".
