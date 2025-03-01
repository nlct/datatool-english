# English Language Module for datatool v3.0+ (datatool-english)

Version %%VERSION%% (%%DATE%%)

Author: Nicola L. C. Talbot [dickimaw-books.com](https://www.dickimaw-books.com/)

Licence: LPPL

Home Page: https://github.com/nlct/datatool-english

Required Packages: 
[datatool](https://ctan.org/pkg/datatool) (3.0+),
[tracklang](https://ctan.org/pkg/tracklang) (1.6.4+)

Provides English language localisation support for
the `datatool` package (v3.0+). Encoding support for UTF-8 and ISO-8859-1
(Latin 1). Any other encoding will be treated as US-ASCII.
The `*.ldf` files should all be placed on TeX's path.

These files don't require any explicit loading. They will
automatically be input by `datatool-base.sty` (or relevant
supplementary package) if they are found and required by the
`tracklang` localisation settings. See the `datatool` and `tracklang` user
manuals for further details.

This bundle is specific to language support or particular
language+region combinations where the region default depends on the
language. Region files (such as `datatool-GB.ldf`) are provided
with `datatool-regions` which needs to be installed separately. This
separation allows arbitrary mix of language and region.

Example:

    \documentclass[en-GB]{article}
    \usepackage{datatool-base}% v3.0
    \newcommand{\mylist}{élan,elephant,élite,elk}
    \begin{document}
    Currency: \DTLdecimaltocurrency{1234.56}{\result}\result.
    
    Original list: \DTLformatlist{\mylist}.
    
    \DTLsortwordlist{\mylist}{\DTLsortwordcasehandler}
    Sorted list: \DTLformatlist{\mylist}.
    \end{document}

If `datatool-english` is correctly installed, the result will be:

 > Currency: £1,234.56.  
 > Original list: élan, elephant, élite and elk.  
 > Sorted list: élan, elephant, élite and elk.

Otherwise the result will be:

 > Currency: £1,234.56.  
 > Original list: élan, elephant, élite & elk.  
 > Sorted list: elephant, elk, élan & élite.

(This assumes the region file `datatool-GB.ldf` provided with
`datatool-regions` is also installed.)

The language doesn't need to be an official language for the region.
For example:

    \documentclass{article}
    \usepackage[locales={en-BE}]{datatool-base}% v3.0
    \newcommand{\mylist}{élan,elephant,élite,elk}
    \begin{document}
    Currency: \DTLdecimaltocurrency{1234.56}{\result}\result.
    
    Original list: \DTLformatlist{\mylist}.
    
    \DTLsortwordlist{\mylist}{\DTLsortwordcasehandler}
    Sorted list: \DTLformatlist{\mylist}.
    \end{document}

If both `datatool-english.ldf` (provided with this bundle) and 
`datatool-BE.ldf` (provided with `datatool-regions`) are installed,
the result will be:

 > Currency: 1.234,56€.  
 > Original list: élan, elephant, élite and elk.  
 > Sorted list: élan, elephant, élite and elk.


See also:

 - [`datatool-regions` (GitHub)](https://github.com/nlct/datatool-regions)
 - [Localisation with datatool v3.0+](https://www.dickimaw-books.com/latex/tracklang/datatool-locale.shtml).

This bundle also includes limited support for Old English
(Anglo-Saxon) mainly to provide an example for a language that has
multiple scripts (in this case, Latin and Runic). The language codes
are `ang-Latn` for Anglo-Saxon Latin Script and `ang-Runr`
for Anglo-Saxon Runic Script. There's only support for UTF-8.

This material is subject to the LaTeX Project Public License.
See http://www.ctan.org/license/lppl1.3 for the details of that
license.
