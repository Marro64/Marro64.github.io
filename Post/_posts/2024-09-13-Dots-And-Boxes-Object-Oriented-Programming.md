---
layout: post
---

For my minor (pre-master) in Techinal Computer Science we were tasked to design and implement a game of Dots and Boxes played via a Command-Line. User-controlled or AI-controlled clients connect to a server following a protocol defined by the course to play a game of Dots and Boxes between two (AI or physical) players. The clients and server are completely custom designed and implemented, and the predefined protocol allowed for compatibility between servers and clients of different groups. 

![Screenshot of the game](/assets/images/{{ page.slug | slugify }}/ingame.png)


This project includes an elaborate design of classes and their methods and relations. Everything was implemented with full [JavaDoc documentation](Dots-and-Boxes). and a number of unit tests. Several diagrams were created for the project, some are included below. All diagrams and an extensive demonstration and discussion of the project can be found in the [report](https://github.com/Marro64/TicTacToe/blob/main/Programming%20Project%20Report%20Minor-2.pdf). Finally, the [source code][code] can be found on [GitHub][code].

![Class diagram of the client](/assets/images/{{ page.slug | slugify }}/client-class-diagram.png)

![State diagram of the client](/assets/images/{{ page.slug | slugify }}/client-state-diagram.png)

![Sequence diagram of the client making a move](/assets/images/{{ page.slug | slugify }}/client-move-sequence-diagram.png)

[code]: https://github.com/Marro64/Dots-and-Boxes