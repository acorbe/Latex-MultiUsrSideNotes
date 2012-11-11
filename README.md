MultiUsrSideNotes
=================

A LaTex package allowing several users to put side notes in a paper, e.g. for reviewing purpose. A login-like procedure allows different author notes to be distinguished by tags and colors.

USAGE: 

```latex
%Login phase - to be put in the header of the document before `\begin{document}`
\SnNewUserID[UserDistinguishing char, e.g. °, default = *]{UserInitial e.g. AC}{NameOfTheCommandToMakeANewNote e.g. ACNote)}

%Example:
\SnNewUserID[*]{AC}{ACNote}
%generates the LaTex command `\ACNote{<myNote>}`. When called it generates a side notes marked by `*` owing to the user whose initials are `AC`.
```

Up to six users are supported so far. The colors distinguishing their notes, assinged according to login order, are 
```latex
\SnAddColor{yellow}
\SnAddColor{blue}
\SnAddColor{green}
\SnAddColor{gray}
\SnAddColor{red}
\SnAddColor{pink}%.
```

