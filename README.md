# datatool-english
Language support for datatool.sty v3.0+

As from version 3.0, the `datatool` package will provide
localisation support (via the [`tracklang`](https://ctan.org/pkg/tracklang) package).
This `datatool-english` bundle provides support for English.

Note that the [`datatool-regions`](https://github.com/nlct/datatool-regions)
bundle provides the language-independent region ldf files. Both
`datatool-regions` and `datatool-english` need to be installed for
regional English support.

If a pre-3.0 version of `datatool` is installed, these ldf files
will be ignored.

Example:
```latex
\documentclass[en-GB]{article}
\usepackage{datatool-base}% v3.0
\newcommand{\mylist}{élan,elephant,élite,elk}
\begin{document}
Currency: \DTLdecimaltocurrency{1234.56}{\result}\result.

Original list: \DTLformatlist{\mylist}

\DTLsortwordlist{\mylist}{\DTLsortwordcasehandler}
Sorted list: \DTLformatlist{\mylist}
\end{document}
```
If `datatool-english` and `datatool-regions` are correctly installed, 
the result will be:

 > Currency: £1,234.56.  
 > Original list: élan, elephant, élite and elk  
 > Sorted list: élan, elephant, élite and elk

If `datatool-regions` is installed but `datatool-english` isn't
installed, then the result will be:

 > Currency: £1,234.56.  
 > Original list: élan, elephant, élite & elk  
 > Sorted list: elephant, elk, élan & élite

If `datatool-regions` isn't installed but `datatool-english` is
installed, then the result will be:

 > Currency: $1,234.56.  
 > Original list: élan, elephant, élite and elk  
 > Sorted list: élan, elephant, élite and elk

The separation of region and language support means that you can mix
and match without requiring the exact _lang_`-`_region_ file.

Example:
```latex
\documentclass{article}
\usepackage[locales={en-BE}]{datatool-base}% v3.0
\newcommand{\mylist}{élan,elephant,élite,elk}
\begin{document}
Currency: \DTLdecimaltocurrency{1234.56}{\result}\result.

Original list: \DTLformatlist{\mylist}

\DTLsortwordlist{\mylist}{\DTLsortwordcasehandler}
Sorted list: \DTLformatlist{\mylist}
\end{document}
```
If `datatool-english` and `datatool-regions` are correctly installed, 
the result will be:

 > Currency: €1.234,56.  
 > Original list: élan, elephant, élite and elk  
 > Sorted list: élan, elephant, élite and elk

This bundle also includes limited support for Old English
(Anglo-Saxon) mainly to provide an example for a language that has
multiple scripts (in this case, Latin and Runic). The language codes
are `ang-Latn` for Anglo-Saxon Latin Script and `ang-Runr`
for Anglo-Saxon Runic Script. There's only support for UTF-8.

Further reading: [Localisation with datatool v3.0+](https://www.dickimaw-books.com/latex/tracklang/datatool-locale.shtml)

This material is subject to the LaTeX Project Public License.
See http://www.ctan.org/license/lppl1.3 for the details of that license.

https://www.dickimaw-books.com/
