# datatool-english
English language support for datatool.sty v3.0+

As from version 3.0, the `datatool` package will provide
localisation support (via the [`tracklang`](https://ctan.org/pkg/tracklang) package).
This `datatool-english` bundle provides support for English and
limited support for Old English.

Some files in this repository use fonts from the Runic Unicode
Block, such as ᚠᚢᚦᚩᚱᚳ. If you see rectangles instead of Runic
characters at the end of the previous sentence, you will need to
install a Runic font to view them. The documentation uses Noto Sans Runic with
`fontspec` and LuaLaTeX.

Note that the [`datatool-regions`](https://github.com/nlct/datatool-regions)
bundle provides the language-independent region `.ldf` files. Both
`datatool-regions` and `datatool-english` need to be installed for
regional English support.

If a pre-3.0 version of `datatool` is installed, these LDF files
will be ignored.

Example:
```latex
\documentclass[en-GB]{article}
\usepackage{datatool-base}% v3.0
\newcommand{\mylist}{elephant,élite,elk,élan}
\begin{document}
Currency: \DTLdecimaltocurrency{1234.56}{\result}\result.

Original list: \DTLformatlist{\mylist}.

\DTLsortwordlist{\mylist}{\DTLsortwordcasehandler}
Sorted list: \DTLformatlist{\mylist}.
\end{document}
```
If `datatool-english` and `datatool-regions` are both correctly installed, 
the result will be:

 > Currency: £1,234.56.  
 > Original list: elephant, élite, elk and élan.  
 > Sorted list: élan, elephant, élite and elk.

If `datatool-regions` is installed but `datatool-english` isn't
installed, then the result will be:

 > Currency: £1,234.56.  
 > Original list: elephant, élite, elk & élan.  
 > Sorted list: elephant, elk, élan & élite.

If `datatool-regions` isn't installed but `datatool-english` is
installed, then the result will be:

 > Currency: $1,234.56.  
 > Original list: elephant, élite, elk and élan.  
 > Sorted list: élan, elephant, élite and elk.

The separation of region and language support means that you can mix
and match without requiring the exact _lang_`-`_region_ file.

For example:
```latex
\documentclass{article}
\usepackage[locales={en-BE}]{datatool-base}% v3.0
\newcommand{\mylist}{elephant,élite,elk,élan}
\begin{document}
Currency: \DTLdecimaltocurrency{1234.56}{\result}\result.

Original list: \DTLformatlist{\mylist}.

\DTLsortwordlist{\mylist}{\DTLsortwordcasehandler}
Sorted list: \DTLformatlist{\mylist}.
\end{document}
```

If both `datatool-english.ldf` (provided with this bundle) and 
`datatool-BE.ldf` (provided with `datatool-regions`) are installed,
the result will be:

 > Currency: 1.234,56€.  
 > Original list: elephant, élite, elk and élan.  
 > Sorted list: élan, elephant, élite and elk.

## Old English (Anglo-Saxon)

This bundle also includes limited support for Old English
(Anglo-Saxon) mainly to provide an example for a language that has
multiple scripts (in this case, Latin and Runic). The language codes
are `ang-Latn` for Anglo-Saxon Latin Script and `ang-Runr`
for Anglo-Saxon Runic Script. There's only support for UTF-8.

**Note that the script refers to the source code script.**
For example, suppose a package provides a command called, say
`\runic`, which expects Latin characters in the argument but the
font encoding ensures that those characters appear as runes in the
PDF (for example, the hypothetical command `\runic{fuþorc}` in the
source code would be rendered as ᚠᚢᚦᚩᚱᚳ in the PDF). In this case,
the source is Latin and so `ang-Latn` is needed when specifying the
locale.

If, however, the source code actually contains characters from
the Runic Unicode block (with an appropriate font that supports
those characters), then the source is Runic and so `ang-Runr`
is needed when specifying the locale.

Further reading: [Localisation with datatool v3.0+](https://www.dickimaw-books.com/latex/tracklang/datatool-locale.shtml)

This material is subject to the LaTeX Project Public License.
See http://www.ctan.org/license/lppl1.3 for the details of that license.

https://www.dickimaw-books.com/
