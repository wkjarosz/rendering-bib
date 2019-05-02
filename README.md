# rendering-bib
This repo houses the master bibliography file that I use for my academic research (containing 2000+ entries), released here in case it will be useful to others. It contains publications mostly in computer graphics, rendering, transport theory, and statistics. The bib files are automatically generated from my [Zotero](https://www.zotero.org/) library using the [Better-BibTeX](https://github.com/retorquere/zotero-better-bibtex) addon.

# Motivation
This repo grew out of my frustration of having to repeatedly search/download bib entries or copy-paste from prior projects (and subsequently correct) in every research project I work on. Instead, I decided to assemble the vast majority of my previously cited papers into a single master bib file which I would use as a starting point for all projects.

# Usage
The main bibliography is in [rendering-bib.bib](rendering-bib.bib). To ensure consistent naming of journals, publishers, etc. this bibliography makes extensive use of `@string`s which are defined in [strings-full.bib](strings-full.bib).

## Examples

[rendering-bib.tex](rendering-bib.tex) and [rendering-bibla.tex](rendering-bibla.tex) contain full LaTeX + BibTeX and LaTeX + BibLaTeX source code for producing the entire bibliography. The [examples/](examples/) directory includes precompiled pdfs for both of these: ([BibTeX version](examples/rendering-bib.pdf), and [BibLaTeX version](examples/rendering-bibla.pdf)).

## BibTeX
To include this in your own LaTeX project using BibTeX, you'd do something like this
```
\bibliography{strings-full,rendering-bib}
```

You will likely need to add on some of your own entries. I recommend you do so in a separate bib file, e.g. `additional.bib`, so you'd use:
```
\bibliography{strings-full,rendering-bib,additional}
```

A benefit of putting the strings in a different bib file is that you can redefine the venues and publisher macros to abbreviated version by creating a `strings-abbrv.bib` file (e.g. when needing to squeeze space for submission), and issuing:
```
\bibliography{strings-abbrv,rendering-bib,additional}
```
instead.

## BibLaTeX
If you use BibLaTeX, you'd instead add the following to your preamble (somewhere after you include the biblatex package):
```
\addbibresource{strings-full.bib}
\addbibresource{rendering-bib.bib}
```

Then, you would add the bibliography in the main paper by issuing the command:
```
\printbibliography
```

With BibLaTeX, you can also easily filter the bibliography. For instance, you could list articles, conference papers, books, and theses separately:
```
\printbibliography[type=article,title={Journal Articles}]
\printbibliography[type=inproceedings,title={Conference Papers}]
\printbibliography[type=book,title={Books}]
\printbibliography[type=thesis,title={Theses}]
\printbibliography[nottype=thesis,nottype=book,nottype=inproceedings,nottype=article,title={Everything Else}]
```

Note that if you use `\nocite{*}`, compiling can take quite some time, especially with biber/BibLaTeX.

## Overleaf
The bibliography is also [available through Overleaf](https://v2.overleaf.com/read/pkthgyqxhcgk
). You can include it in your own Overleaf projects following [these directions](https://www.overleaf.com/learn/how-to/Can_I_share_files_(e.g._.bib_and_some_graphics)_across_my_projects%3F).

# Contributing
I gladly accept pull requests with corrections. While I intend to keep extending this bibliography – and I welcome pull requests with additions – my goal is to restrict the entries to ones that are relevant to my own research to avoid an unnecessary explosion of entries.

If you do have suggestions for additions/corrections, please follow these guidelines:
* Use the relevant `@string`s defined in [strings-full.bib](strings-full.bib). In particular, conferences such as SIGGRAPH and EGSR were published differently across the years (sometimes as a journal, sometimes just a proceedings, sometimes both). Make sure to use the correct `@string`. In years that an article is published both as a proceedings and in a journal, prefer the journal version.
* Include the full first name of all authors, instead of just first initials. The bibliography style may abbreviate to first initials, but its impossible to go the other direction.
* Include a DOI entry if appropriate.
* Include the page range (and use an en-dash `--`).
* Do not include a url field, or other superfluous fields that are often included in bib files from ACM Portal (articlenum, acmid, etc).
* Do not force a particular capitalization for the entire title but do wrap proper nouns in braces to force capitalization of just those words. Wrap the entire word instead of just the first letter, e.g. `{Monte} {Carlo}` and not `{M}onte {C}arlo` (the latter can cause kerning issues).

# Acknowledgements
The entries were primarily seeded from the bibliographies of my prior [publications](https://cs.dartmouth.edu/~wjarosz/#publications). I also incorporated Jim Arvo's excellent graphics, physics, and transport bib entries (which are [still available on the wayback machine](https://web.archive.org/web/20120117002445/http://www.ics.uci.edu/~arvo/software.html)), and Per Christensen's [importance bibliography](https://www.seanet.com/~myandper/importance.htm).

While they are not included here, you may also be interested in Ian Ashdown's extensive [radbib bibliography](http://www.helios32.com/radbib.bib) with some 3000+ references to mostly radiosity literature.



