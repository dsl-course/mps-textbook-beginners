# Programming with JetBrains MPS &mdash; Textbook for Beginners

This document contains an outline of a textbook on JetBrains Meta Programming System ([JetBrains MPS](https://jetbrains.com/mps)) being written by [Mikhail Barash](https://twitter.com/mikhail_barash).
The purpose of this document is to have a discussion on the content structure of the textbook with [MPS community](https://twitter.com/jetbrains_mps) members.

The textbook is meant for those without any prior experience on JetBrains MPS or language engineering.
The author has [some experience](http://dsl-course.org) in teaching courses on MPS, and this book is planned as an embodiment of the methodological approaches used in different teaching settings.

The structural unit of the book is a **double-page spread**, rather than a page.
Each spread is a finished piece of information &mdash; it has self-contained material on a particular topic.
Some topics span over several spreads, and in such cases each of the spreads is devoted to a single subtopic.

The textbook is divided into three parts:
- _MPS as a tool for [textual UIs](https://peerj.com/articles/800/?utm_source=TrendMD&utm_campaign=PeerJ_TrendMD_0&utm_medium=TrendMD)_
- _MPS as a [modelling tool](http://dslbook.org/)_
- _MPS as a tool for [extending existing languages](https://www.voelter.de/data/pub/PPPJ.pdf)_

This choice and order of the parts is explained by a desire to avoid burdening the reader with language engineering terminology (from our experience, even "AST" scares off beginners.) We start with known terminology &ndash; _classes, interfaces, enumerations_ &ndash; and slowly revise key notions and ideas using "appropriate" terminology.
Moreover, the choice of the parts reflects [typical patterns](https://languageengineering.io/high-level-structure-of-dsls-three-patterns-7375c8baa2d3) for building a software language.

Here are some of the highlights of the content of the textbook.
- As the intro text of each of the parts of the book is still a double-page spread, there is no explicit separation into parts for the reader.
- The book starts with a general discussion on what a **workbench** is (not only _language workbench_). 
- At first, MPS is presented as a tool to define **textual user interfaces.** We start with familiar notions of _classes_, _interfaces_, _enumerations_, etc. and throught this part, we introduce their "counterparts" in MPS. For example, _classes_ become _concepts_ and so on. 
- Each of the three parts of the book has a **running example** that we develop from scratch until completition during the course of the corresponding part.
- In the first part, we develop a textual UI for _Invoice Calculator_, introducing and showcasing necessary MPS notions.
- We postpone as much as possible discussing **language aspects.** When we finally have to introduce aspects, we do not expose the reader to details unnecessary at a particular point. For example, discussion of `Editor` aspect tries to avoid making a big deal of projectional editing (see below). `Actions` aspect in not mentioned until the second part of the book, where it comes naturally in one of the examples.
- We then discuss `Intentions` aspect and make a point about importance of domain-specific error support. We discuss an implementation of _Invoice Calculator_ in Excel for comparison.
- **Code generation** is discussed throught several spreads of the book, and we start with `TextGen` aspect, where we define a generator for _Invoice Calculator_
that generates [RTF](https://en.wikipedia.org/wiki/Rich_Text_Format) files.
- We continue with **code generation** with `Generator` aspect: we define a generator for _Invoice Calculator_ to XML. 
- At this point we make an excursion to XML/XSLT and give a conceptual comparison of `Generator` aspect and [XSL transformations](https://en.wikipedia.org/wiki/XSLT#Example_1_(transforming_XML_to_XML)).
- We then continue with **generating Java code** with `Generator`. We deliberatly discuss Java code generation _after_ RTF and XML to address a frequent opinion of the newcomers that MPS only allows generating Java code.
- **Projectional editing** does often scary off beginners by its perceived "clumsiness" and [limitations](https://link.springer.com/chapter/10.1007/978-3-319-11245-9_3). That is why it is not "introduced" until this moment. We try to make the point that there is nothing special in the fact that MPS (only) supports projectional editing, by discussing that most of the functionality of a traditional text editor is replicated in MPS. Putting projectional editing to the backstage was a major decision we made about this book, and it still remains to see whether it makes a difference. We also discuss in details `Actions` aspect.
- In the second part of the book, we use MPS as a modelling tool, i.e., we discuss the raison d'être application of MPS &mdash; **implementation of domain-specific languages.** Running example of this part is `Entities` language; we define code generators into Java, JavaScript/React and Excel/VBA. This selection of target languages is motivated by the need to communicate to the reader that MPS can be used to generate web applications as well as "legacy code".
- We revise the metaphor of _OOP counterparts in MPS_ that we introduced in the beginning of the first part, and encourage the reader to focus on notions used in language engineering.
- We return again to **code generation** with `Generator` aspect, where we discuss in more details reductions, quotations, mapping labels, etc.
- We then continue with **type system** and **data-flow analysis** for `Entities` language. By this time, the reader has implemented a tiny domain-specific language. Our goal here was to describe the development of a language from scratch within one "chapter". The second part is concluded by a discussion on evolution of `Entities` language and language migration in MPS.
- The third part of the book is devoted to using MPS to extend `baseLanguage` &mdash; we introduce several **extensions of Java**, talk again about `Actions`, `Constraints`, and `Generator` aspects. We also discuss about extending `Entities` language.
- We give an overview of **language composition** ([reference, extension, reuse, embedding](https://link.springer.com/chapter/10.1007/978-3-642-35992-7_11)) and talk again about projectional editing and how it enables language composition. However, we do not go into further details on language reference/reuse/embedding because these topics, in our opinion, should be covered in a more advanced book.
- For the same reasons, we **do not** discuss any of the [MPS extensions](https://github.com/JetBrains/MPS-extensions), such as [grammar cells](https://www.mathematik.uni-marburg.de/~seba/publications/grammar-cells.pdf) or [`PlainTextGen`](https://github.com/DSLFoundry/mps-plaintextgen).
- We do not discuss **testing.** This is a drawback, but discussing this topic might complicate reader's perception of already non-trivial material. The purpose on the textbook is to give an _introduction_ to MPS: we don't aim at preparing a reader for _deploying_ a language. Another important topic that is left for a more advanced book is **debugging.**
- We explicitly mark each spread of the book with "difficulty" level, suggesting **several study paths** for those interested in superficial acquaintance with MPS, those who already have some basic knowledge, or those who want to study more "advanced" topics.
- Finally, because we revise MPS idioms, notions, and used terminology throughout the book, and because of the very layout of the book, some repetitions of the material are unavoidable.

Below we list the **spreads** of the book.

|Spread #|Topic|
|---|---|
|0|What is MPS?|
|1&mdash;2|MPS as a Tool for Textual User Interfaces|
|3&mdash;6|Object-Oriented Programming in MPS|
|7|Intentions and Quickfixes|
|8&mdash;10|Generating Text Output with `TextGen`|
|11|Generating XML Output with `Generator`|
|12&mdash;13|Generating Java Code with `Generator`|
|14&mdash;16|Projectional Editing: Pros and Cons|
|17&mdash;18|Tabular and Graphical projections|
|19|MPS as a Modelling Tool|
|20&mdash;21|Looking at Code Through MPS Prism|
|22&mdash;24|`Entities` Example|
|25&mdash;26|Scoping Rules and `Constraints`|
|27&mdash;29|Generating Java Code with `Generator`|
|30&mdash;31|Generating JavaScript Code|
|32|Generating VBA Code|
|33&mdash;34|Checking Domain Code: Type Systems|
|35|Checking Domain Code: Data-Flow Analysis|
|36|Evolution of Languages|
|37&mdash;39|MPS as a Tool for Extending Existing Languages|Java/`baseLanguage`|
|40|MPS in Practice|

# When Will the Textbook Be Ready?

Rough estimate is Q2&ndash;Q3 2020.

It takes a significant amount of time not only to prepare the content of a spread, but also to layout it in a proper and engaging way.
Inspired by [this](https://images-na.ssl-images-amazon.com/images/I/91x2E4SxBsL.jpg), [this](https://images-na.ssl-images-amazon.com/images/I/91w5VzwEkFL.jpg) and [this](https://www.amazon.co.uk/Help-Your-Science-Step-Step/dp/1409383466), we try to use encyclopedia-style layout (_only layout &mdash; not content_), for example, with boxes for extra material, and so on.

The book will be published electronically and will be open-source: all spreads will be published in Adobe Illustrator format (layers preserved etc.) so that they could be (re)used for creating teaching materials.
