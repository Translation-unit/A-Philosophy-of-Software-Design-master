# Introduction（引言）

> **It’s All About Complexity（关于复杂性的一切）**

Writing computer software is one of the purest creative activities in the history of the human race. Programmers aren’t bound by practical limitations such as the laws of physics; we can create exciting virtual worlds with behaviors that could never exist in the real world. Programming doesn’t require great physical skill or coordination, like ballet or basketball. All programming requires is a creative mind and the ability to organize your thoughts. If you can visualize a system, you can probably implement it in a computer program.

编写计算机软件是人类历史上最纯粹的创作活动之一。程序员不受物理定律等实际限制的约束；我们可以用现实世界中永远不可能存在的行为创造令人兴奋的虚拟世界。编程并不像芭蕾或篮球那样需要很强的身体技巧或协调能力。编程所需要的是创造性思维和组织思维的能力。如果你能把一个系统具象化，你也许就能计算机程序中实现它。

This means that the greatest limitation in writing software is our ability to understand the systems we are creating. As a program evolves and acquires more features, it becomes complicated, with subtle dependencies between its components. Over time, complexity accumulates, and it becomes harder and harder for programmers to keep all of the relevant factors in their minds as they modify the system. This slows down development and leads to bugs, which slow development even more and add to its cost. Complexity increases inevitably over the life of any program. The larger the program, and the more people that work on it, the more difficult it is to manage complexity.

这意味着，编写软件的最大限制是去理解我们正创建的系统的能力。随着程序的演变和获得更多的功能，它变得复杂，其组件之间有微妙的依赖关系。随着时间的推移，复杂性不断积累，程序员在修改系统时，越来越难将所有相关因素记在脑海中。这会减慢开发速度，并导致bug，从而使开发速度更加慢，并增加其成本。在任何程序的生命周期中，复杂性都会不可避免地增加。程序越大，参与其中的人员越多，对于复杂性的管理就越困难。

Good development tools can help us deal with complexity, and many great tools have been created over the last several decades. But there is a limit to what we can do with tools alone. If we want to make it easier to write software, so that we can build more powerful systems more cheaply, we must find ways to make software simpler. Complexity will still increase over time, in spite of our best efforts, but simpler designs allow us to build larger and more powerful systems before complexity becomes overwhelming.

好的开发工具可以帮助我们处理复杂性，在过去的几十年中也创造了许多出色的工具。但我们仅用工具就能做的事情是有限的。如果我们想让编写软件变得更容易，以便我们能以更低的成本构建更强大的系统，我们就必须找到使软件更简单的方法。尽管我们尽最大的努力，复杂性仍然会随着时间的推移而增加，但是更简单的设计会使我们在复杂性变得无法抗拒之前构建更大、更强大的系统。

There are two general approaches to fighting complexity, both of which will be discussed in this book. The first approach is to eliminate complexity by making code simpler and more obvious. For example, complexity can be reduced by eliminating special cases or using identifiers in a consistent fashion.

有两种方法可以对抗复杂性，这两种方法都将在本书中讨论。第一种方法是通过使代码更简单明显来消除复杂性。例如，可以通过消除特殊情况或以一致的方式使用标识符来降低复杂性。

The second approach to complexity is to encapsulate it, so that programmers can work on a system without being exposed to all of its complexity at once. This approach is called modular design. In modular design, a software system is divided up into modules, such as classes in an object-oriented language. The modules are designed to be relatively independent of each other, so that a programmer can work on one module without having to understand the details of other modules.

Because software is so malleable, software design is a continuous process that spans the entire lifecycle of a software system; this makes software design different from the design of physical systems such as buildings, ships, or bridges. However, software design has not always been viewed this way. For much of the history of programming, design was concentrated at the beginning of a project, as it is in other engineering disciplines. The extreme of this approach is called the waterfall model, in which a project is divided into discrete phases such as requirements definition, design, coding, testing, and maintenance. In the waterfall model, each phase completes before the next phase starts; in many cases different people are responsible for each phase. The entire system is designed at once, during the design phase. The design is frozen at the end of this phase, and the role of the subsequent phases is to flesh out and implement that design.

Unfortunately, the waterfall model rarely works well for software. Software systems are intrinsically more complex than physical systems; it isn’t possible to visualize the design for a large software system well enough to understand all of its implications before building anything. As a result, the initial design will have many problems. The problems do not become apparent until implementation is well underway. However, the waterfall model is not structured to accommodate major design changes at this point \(for example, the designers may have moved on to other projects\). Thus, developers try to patch around the problems without changing the overall design. This results in an explosion of complexity.

Because of these issues, most software development projects today use an incremental approach such as agile development, in which the initial design focuses on a small subset of the overall functionality. This subset is designed, implemented, and then evaluated. Problems with the original design are discovered and corrected, then a few more features are designed, implemented and evaluated. Each iteration exposes problems with the existing design, which are fixed before the next set of features is designed. By spreading out the design in this way, problems with the initial design can be fixed while the system is still small; later features benefit from experience gained during the implementation of earlier features, so they have fewer problems.

The incremental approach works for software because software is malleable enough to allow significant design changes partway through implementation. In contrast, major design changes are much more challenging for physical systems: for example, it would not be practical to change the number of towers supporting a bridge in the middle of construction.

Incremental development means that software design is never done. Design happens continuously over the life of a system: developers should always be thinking about design issues. Incremental development also means continuous redesign. The initial design for a system or component is almost never the best one; experience inevitably shows better ways to do things. As a software developer, you should always be on the lookout for opportunities to improve the design of the system you are working on, and you should plan on spending some fraction of your time on design improvements.

If software developers should always be thinking about design issues, and reducing complexity is the most important element of software design, then software developers should always be thinking about complexity. This book is about how to use complexity to guide the design of software throughout its lifetime.

This book has two overall goals. The first is to describe the nature of software complexity: what does “complexity” mean, why does it matter, and how can you recognize when a program has unnecessary complexity? The book’s second, and more challenging, goal is to present techniques you can use during the software development process to minimize complexity. Unfortunately, there isn’t a simple recipe that will guarantee great software designs. Instead, I will present a collection of higher-level concepts that border on the philosophical, such as “classes should be deep” or “define errors out of existence.” These concepts may not immediately identify the best design, but you can use them to compare design alternatives and guide your exploration of the design space.
