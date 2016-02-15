---
layout:     post
title:      macro-compat-1.1.1 released
author:     Miles Sabin
date:       '2016-02-15 12:00:00'
---

Despite being binary compatible with macro-compat 1.1.0, this release represents a major overhaul of the underlying
implementation and a significant extension to the breadth of the support for 2.11.x style macros on 2.10.x.
<span class="break"></span>This has made it possible to fully support shapeless (as of version 2.3.0) with a single
branch and no Scala version variant source. Given that shapeless contains some fairly large and sophisticated macros
which exploit private internals of the macro API this is a significant milestone and suggests that macro-compat is
ready for wider use.

I would especially like to thank [Dale Wijnand][@dwijnand] for his relentless efforts adding support for features
required by shapeless, and [Chris Hodapp][@clhodapp] for his work on and inspiration in supporting access to macro
internals.

Release notes follow ...

These release notes provide a summary of changes since macro-compat 1.1.0,

* Macro bundle rewrite now more closely matches 2.11.x structure, supporting bundle inheritance and companions.
* Added to c.internal: newTermSymbol, polyType, setInfo, singleType, substituteSymbols, thisType, typeRef
* Added c.internal.decorators (thanks to [@dwijnand][]).
* Added to Symbol: isAbstract, overrides (thanks to [@dwijnand][]).
* Added to Tree: nonEmpty (thanks to [@dwijnand][]).
* Added to Type: finalResultType, paramLists, typeArgs (thanks to [@dwijnand][]).
* dealias implementation match 2.11.x semantics.
* Added support for use of internal ContextReporter (thanks to [@clhodapp][]
* Added support for 2.11 style ImplicitCandidate (thanks to [@dwijnand][]).
* Now uses macro-paradise 2.1.0.
* Added 2.12.0-M3 to the cross build version list (thanks to [@dwijnand][])

Many thanks to everyone who has contributed ideas, enthusiasm and encouragement.

[macro-compat]: https://github.com/milessabin/macro-compat
[mima]: https://github.com/typesafehub/migration-manager
[@clhodapp]: https://twitter.com/clhodapp
[@dwijnand]: https://github.com/dwijnand
