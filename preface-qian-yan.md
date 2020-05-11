# Preface（前言）

People have been writing programs for electronic computers for more than 80 years, but there has been surprisingly little conversation about how to design those programs or what good programs should look like. There has been considerable discussion about software development processes such as agile development and about development tools such as debuggers, version control systems, and test coverage tools. There has also been extensive analysis of programming techniques such as object-oriented programming and functional programming, and of design patterns and algorithms. All of these discussions have been valuable, but the core problem of software design is still largely untouched. David Parnas' classic paper “On the Criteria to be used in Decomposing Systems into Modules” appeared in 1971, but the state of the art in software design has not progressed much beyond that paper in the ensuing 45 years.

80多年来，人们一直在用电子计算机编写程序，但意外的是，关于如何去设计这些程序和什么是好的程序的交流却很少。关于软件开发过程\(如敏捷开发\)和开发工具\(如调试器、版本控制和测试覆盖工具\)已经有了相当多的讨论。还对面向对象编程和函数编程等编程技术以及设计模式和算法进行了广泛的分析。上述这些讨论都是有价值的，但是很大程度上仍然没有触及到软件设计的核心问题。[David Parnas](https://en.wikipedia.org/wiki/David_Parnas)的经典论文“[关于将系统分解成模块的标准](https://www.win.tue.nl/~wstomv/edu/2ip30/references/criteria_for_modularization.pdf)”发表于1971年，但是在随后的45年里，软件设计的发展水平并没有超过这篇论文。

The most fundamental problem in computer science is _problem decomposition_: how to take a complex problem and divide it up into pieces that can be solved independently. Problem decomposition is the central design task that programmers face every day, and yet, other than the work described here, I have not been able to identify a single class in any university where problem decomposition is a central topic. We teach for loops and object-oriented programming, but not software design.

计算机科学中最基本的问题是_问题分解_：如何将一个复杂的问题分割成可以独立解决的部分。问题分解是程序员每天面临的主要设计任务，然而，除了上面描述的工作，我没能在任何一所大学里找到以问题分解为中心主题的课程。我们教循环和面向对象编程，却没有教软件设计。

In addition, there is a huge variation in quality and productivity among programmers, but we have made little attempt to understand what makes the best programmers so much better or to teach those skills in our classes. I have talked with several people I consider to be great programmers, but most of them had difficulty articulating specific techniques that give them their advantage. Many people assume that software design skill is an innate talent that cannot be taught. However, there is quite a bit of scientific evidence that outstanding performance in many fields is related more to high-quality practice than innate ability \(see, for example, Talent is Overrated by Geoff Colvin\).

此外，程序员在产出质量与产出效率上也存在大量差异，但是我们很少去尝试了解优秀的程序员是怎么变得更好的，或者在课堂上去教授这些技能。我曾与一些我认为优秀的程序员交谈过，但是他们大多数都难以清晰地表达出使他们具有优势的特定技术。许多人认为软件设计技能是一种与生俱来的天赋，是无法传授的。然而，有相当多的科学证据表明，在许多领域的杰出表现更多与高水准的实践有关，而不是先天能力（参见，例如，[Geoff Colvin](https://book.douban.com/subject/3424910/)的[Talent Is Overrated](https://book.douban.com/subject/3424910/)）

For many years these issues have perplexed and frustrated me. I have wondered whether software design can be taught, and I have hypothesized that design skill is what separates great programmers from average ones. I finally decided that the only way to answer these questions was to attempt to teach a course on software design. The result is CS 190 at Stanford University. In this class I put forth a set of principles of software design. Students then work through a series of projects to assimilate and practice the principles. The class is taught in a fashion similar to a traditional English writing class. In an English class, students use an iterative process where they write a draft, get feedback, and then rewrite to make improvements. In CS 190, students develop a substantial piece of software from scratch. We then go through extensive code reviews to identify design problems, and students revise their projects to fix the problems. This allows students to see how their code can be improved by applying design principles.

多年来，这些问题使我困惑和沮丧。我想弄明白软件设计是否可以教授，我假设设计技能是区分优秀程序员和普通程序员的关键。我最终决定，回答这些问题的唯一方法就是尝试教授一门软件设计的课程。这门课就是斯坦福大学的CS190。在这门课中我提出了一套软件设计原则。然后，学生通过一系列项目来吸收和实践这些原则。这门课的教学方式类似于传统的英语写作课。在英语课上，学生们采用一种迭代过程的方式，先写一份草稿，得到反馈，然后重写以改进。在CS 190中，学生们从零到一开发一个重要的软件。然后，进行广泛的代码审查，以确定设计的问题，学生通过修改他们的项目解决问题。这样就使得学生知道如何通过应用设计原则来改进他们的代码。

I have now taught the software design class three times, and this book is based on the design principles that emerged from the class. The principles are fairly high level and border on the philosophical \("Define errors out of existence"\), so it is hard for students to understand the ideas in the abstract. Students learn best by writing code, making mistakes, and then seeing how their mistakes and the subsequent fixes relate to the principles.

我现已经教过三次软件设计课，这本书是基于课堂上出现的设计原则。这些原则在哲学上有着相当高的水平和边界（“定义存在的错误”），所以学生很难抽象地理解这些想法。学生最好的学习方法是编写代码，试错，然后思考他们的错误和修复是怎么与这些原则相关联的。

At this point you may well be wondering: what makes me think I know all the answers about software design? To be honest, I don’t. There were no classes on software design when I learned to program, and I never had a mentor to teach me design principles. At the time I learned to program, code reviews were virtually nonexistent. My ideas about software design come from personal experience writing and reading code. Over my career I have written about 250,000 lines of code in a variety of languages. I’ve worked on teams that created three operating systems from scratch, multiple file and storage systems, infrastructure tools such as debuggers, build systems, and GUI toolkits, a scripting language, and interactive editors for text, drawings, presentations, and integrated circuits. Along the way I’ve experienced firsthand the problems of large systems and experimented with various design techniques. In addition, I’ve read a considerable amount of code written by other people, which has exposed me to a variety of approaches, both good and bad.

在这一点上，你很可能会想：是什么让我认为我知道了关于软件设计的所有答案？老实说，我没有。 我学编程的时候没有软件设计的课程，也从来没有导师教我设计原理。 在我学习编程的时候，代码审查几乎不存在。 我对软件设计的想法来源于个人写代码和读代码的经验。 在我的职业生涯中，我用各种语言写了大约25万行代码。我工作的团队从零开始创建了三个操作系统，多个文件存储系统，基础设施工具\(如调试器、构建系统\)和GUI工具包\(一种脚本语言\)，以及用于文本，绘图，演示文稿和集成电路的交互式编辑器。一路上，我亲身体验了大型系统的问题，并尝试了各种设计技术。 此外，我还阅读了其他人写的大量代码，这让我接触到各种各样的方法，有好的也有坏的。

Out of all of this experience, I’ve tried to extract common threads, both about mistakes to avoid and techniques to use. This book is a reflection of my experiences: every problem described here is one that I have experienced personally, and every suggested technique is one that I have used successfully in my own coding.

从所有这些经验中，我尝试提取一些常见的线索，包括要避免的错误和要使用的技术。这本书反映了我的经验：这里描述的每个问题都是我亲身经历过的，每个技术建议都是我在编程中成功使用过的。

I don’t expect this book to be the final word on software design; I’m sure there are valuable techniques that I’ve missed, and some of my suggestions may turn out to be bad ideas in the long run. However, I hope that the book will start a conversation about software design. Compare the ideas in this book with your own experiences and decide for yourself whether the approaches described here really do reduce software complexity. This book is an opinion piece, so some readers will disagree with some of my suggestions. If you do disagree, try to understand why. I’m interested in hearing about things that work for you, things that don’t work, and any other ideas you may have about software design. I hope that the ensuing conversations will improve our collective understanding of software design. I will incorporate what I learn in future editions of this book.

我不希望这本书成为软件设计的最终定论；我相信我错过了一些有价值的技术，从长远来看，我的一些建议可能会变成糟糕的想法。然而，我希望这本书能开启一个关于软件设计的交流。将本书中的思想与你自己的经验进行比较，并自行决定这里描述的方法是否真的降低了软件的复杂性。这本书是一篇观点文章，所以有些读者会不同意我的一些建议。如果你确实不同意，试着去了解为什么。 我希望知道哪些东西对你有用，哪些对你没用，以及你对软件设计的其他想法。我希望接下来的交流会提高我们对软件设计的整体理解。我将把我学到的东西写进这本书的未来版本中。

The best way to communicate with me about the book is to send email to the following address: software-design-book@googlegroups.com

与我沟通这本书的最好方法是发送电子邮件到以下地址：[software-design-book@googlegroups.com](mailto:software-design-book@googlegroups.com)

I’m interested in hearing specific feedback about the book, such as bugs or suggestions for improvement, as well as general thoughts and experiences related to software design. I’m particularly interested in compelling examples that I can use in future editions of the book. The best examples illustrate an important design principle and are simple enough to explain in a paragraph or two. If you would like to see what other people are saying on the email address and participate in discussions, you can join the Google Group software-design-book.

我很乐意听到关于这本书的具体反馈，比如bug或改进建议，以及与软件设计有关的一般想法和经验。我特别希望有引人注目的例子让我可以在本书未来版本中使用的。最好例子可以说明一个重要的设计原则，并且简单到可以用一两个段落解释。如果你想看看其他人在电子邮件上说些什么并想参与讨论，你可以加入到谷歌小组 software-design-book。

If for some reason the software-design-book Google Group should disappear in the future, search on the Web for my home page; it will contain updated instructions for how to communicate about the book. Please don’t send book-related email to my personal email address.

如果因为某种原因，software-design-book 谷歌小组在未来解散，在网上搜索我的主页；它会包含关于如何沟通这本书的更新说明。但请不要发送与书籍相关的电子邮件到我的个人邮箱。

I recommend that you take the suggestions in this book with a grain of salt. The overall goal is to reduce complexity; this is more important than any particular principle or idea you read here. If you try an idea from this book and find that it doesn’t actually reduce complexity, then don’t feel obligated to keep using it \(but, do let me know about your experience; I’d like to get feedback on what works and what doesn’t\).

我建议你对本书中的建议持保留态度。总体目标是降低复杂性；这比你在这里读到的任何原则或想法都重要。如果你尝试了本书中的一个想法，发现它实际上并没有降低复杂性，那么不要强制使用它（但是，一定要你的经验分享给我；我希望得到反馈，什么有效什么无效）。

Many people have offered criticisms or made suggestions that improved the quality of the book. The following people offered helpful comments on various drafts of the book: Jeff Dean, Sanjay Ghemawat, John Hartman, Brian Kernighan, James Koppel, Amy Ousterhout, Kay Ousterhout, Rob Pike, Partha Ranganathan, Keith Schwartz, and Alex Snaps. Christos Kozyrakis suggested the terms “deep” and “shallow” for classes and interfaces, replacing previous terms “thick” and “thin”, which were somewhat ambiguous. I am indebted to the students in CS 190; the process of reading their code and discussing it with them has helped to crystallize my thoughts about design.

许多人提出了批评或建议，提高了这本书的质量。以下这些人对这本书的不同版本给出了有益的评论：Jeff Dean, Sanjay Ghemawat, John Hartman, Brian Kernighan, James Koppel, Amy Ousterhout, Kay Ousterhout, Rob Pike, Partha Ranganathan, Keith Schwartz, and Alex Snaps。Christos Kozyrakis建议用"deep\(深\)"和"shallow\(浅\)"用于类和接口，而不是以前的"thick\(厚\)"和"thin\(薄\)"，这两个词有些模棱两可。我很感谢CS 190的学生；阅读他们代码并与他们讨论的过程有助于我将设计的想法具象化。



