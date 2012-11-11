MultiUsrSideNotes
=================

A LaTeX package allowing *several users* to put *side notes* in a paper, e.g. for reviewing purpose. 
A *login-like procedure* allows authors to distinguish their notes by tags and colors. 
One may want consider the attached file ```MultiUsrSideNotes_Guide_and_example.tex``` as a reference.

USAGE: 
----------------
**Dependencies:**
```latex
% (from MultiUsrSideNotes.sty)
\RequirePackage{xcolor}
\RequirePackage{etoolbox}
```

**Inclusion and activation**: after including the package, it must be explicitly enabled; 
if not, side notes *will not appear* in the final document. 
```latex
\usepackage{MultiUsrSideNotes} 	%inclusion
\settoggle{SnShowNotes}{true}	  %activation - false to disable
```

**Login**: to be put in the header of the document before `\begin{document}`

```latex
\SnNewUserID[a]{b}{c}
%a -> UserDistinguishing char, e.g. °, default = *
%b -> UserInitial e.g. AC
%c -> NameOfTheCommandToMakeANewNote e.g. ACNote
```

*Example*:
```latex
\SnNewUserID[*]{AC}{ACNote}
%generates the LaTex command `\ACNote{<myNote>}`. 
%When called it generates a side notes marked by 
%`*` owing to the user whose initials are `AC`.
```

**Use**:
```latex
\ACNote{Hey, this is my side note.}
%Put a side note whose content is "Hey, this is my side note."
```

**Notes:**

Up to six users are supported so far. The colors distinguishing their notes, which are assinged following the login order, are 
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
