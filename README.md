# rendering-bib
This repo houses the master bibliography file that I use for my academic research (containing 2000+ entries), released here in case it will be useful to others. It contains publications mostly in computer graphics, rendering, transport theory, and statistics. There is a BibTeX version (I plan to release a Biber/BibLaTeX version. Both versions are automatically generated from my [Zotero](https://www.zotero.org/) library using the [Better-BibTeX](https://github.com/retorquere/zotero-better-bibtex) addon.

# Motivation
This repo grew out of my frustration of having to repeatedly search/download bib entries or copy-paste from prior projects (and subsequently correct) in every research project I work on. Instead, I decided to assemble the vast majority of my previously cited papers into a single master bib file which I would use as a starting point for all projects.

# Usage
The main bibliography is in `rendering-bib.bib`, with many string macros defined in `strings-full.bib` to ensure consistent naming of journals, publishers, etc. If you are using BibTeX, you'd use this like

```
\bibliography{strings-full,rendering-bib}
```

The nice thing about putting the strings in a different bib file is that you can redefine the venues and publisher macros to abbreviated version by creating a `strings-abbrv.bib` file (e.g. when needing to squeeze space for submission), and issuing:
```
\bibliography{strings-abbrv,rendering-bib}
```
instead.

# Contributing
I gladly accept pull requests with corrections. While I intend to keep extending this bibliography – and I welcome pull requests with additions – my goal is to restrict the entries to ones that are relevant to my own research to avoid an unnecessary explosion of entries.

If you do have suggestions for additions/corrections, please follow these guidelines:
* Use the relevant @strings defined in `strings-full.bib`. In particular, conferences such as SIGGRAPH and EGSR were published differently across the years (sometimes as a journal, sometimes just a proceedings, sometimes both). Make sure to use the correct @string.
* Include the full first name of all authors, instead of just first initials. The bibliography style may abbreviate to first initials, but its impossible to go the other direction.
* Include a DOI entry if appropriate.
* Include the page range (and use an en-dash '--').
* Do not include a url field, or other superfluous fields that are often included in bib files from ACM Portal (articlenum, acmid, etc).
* Do not force a particular capitalization for the entire title. Use sentence case, and wrap proper nouns in braces to force capitalization of just those words. Wrap the entire word instead of just the first letter (the latter can cause kerning issues)

# Acknowledgements
The bibliography entries were primarily seeded from the bibliographies of my prior [publications](https://cs.dartmouth.edu/~wjarosz/#publications). I also incorporated Jim Arvo's excellent graphics, physics, and transport bib entries which are [still available on the wayback machine](https://web.archive.org/web/20120117002445/http://www.ics.uci.edu/~arvo/software.html), and Per Christensen's [importance bibliography](https://www.seanet.com/~myandper/importance.htm).

While they are not included here, you may also be interested in Ian Ashdown's extensive [radbib bibliography](http://www.helios32.com/radbib.bib) with some 3000+ references to mostly radiosity literature.



