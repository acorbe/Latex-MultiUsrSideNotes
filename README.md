MultiUsrSideNotes
=================

A LaTeX package allowing *several users* to put *side notes* in a paper, e.g. for reviewing purpose. 
A *login-like procedure* allows authors to distinguish their notes by tags and colors. 
One may want consider the attached file ```MultiUsrSideNotes_Guide_and_example.tex``` as a reference.

USAGE: 
----------------
**Required packages:** [*xcolor*](http://www.ctan.org/tex-archive/macros/latex/contrib/xcolor), [*etoolbox*](http://www.ctan.org/tex-archive/macros/latex/contrib/etoolbox).


**Inclusion and activation**: after inclusion the package must be explicitly enabled; 
if not, side notes *will not appear* in the final document. 
```latex
\usepackage{MultiUsrSideNotes} 	%inclusion
\settoggle{SnShowNotes}{true}	  %activation - false to disable
```

**Login**: login command must be put in the header of the document, i.e. before `\begin{document}` according to
the following syntax

```latex
\SnNewUserID[a]{b}{c}
```
-   `a` -> User Distinguishing tag; single char e.g. °, default = *

-   `b` -> User initials, e.g. AC

-   `c` -> Keyword which makes new notes owing to the current user, e.g. ACNote


*Example*:
```latex
\SnNewUserID[*]{AC}{ACNote}
```
generates the LaTex command `\ACNote{<myNote>}`. When called, it generates a side notes marked by 
`*` owing to the user whose initials are `AC`.

**Making a note**: The previously generated command `c` can be used to insert a new side note.

*Example*:
```latex
\ACNote{Hey, this is my side note.}
```
inserts a side note whose content is "Hey, this is my side note."

**Remarks:** Up to six users are supported so far. The colors distinguishing their notes, which are assinged following the login order, are 
```latex
% (from MultiUsrSideNotes.sty)
\SnAddColor{yellow}
\SnAddColor{blue}
\SnAddColor{green}
\SnAddColor{gray}
\SnAddColor{red}
\SnAddColor{pink}
```
.
