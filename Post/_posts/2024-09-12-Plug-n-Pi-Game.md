---
layout: post
---

Plug'n'Pi is a motion-controlled endless-runner game running on a Raspberry Pi with a web server for sharing scores and starting the game. The main input is a webcam which uses OpenCV facial-detection to see where the player is and move the player character accordingly. The Raspberry Pi does not have an input connected for starting the game, this is instead accomplished via a game server which stores high scores and can send game start commands to the Pi. The focus on this project is the server connectivity features.

![Screenshot of the game](/assets/images/{{ page.slug | slugify }}/game.png)

The game displays a QR-Code which users scan to connect their user account to the Pi and access the website to press the start button and to view high scores. When the Raspberry Pi is started, it requests an identifier from the server which it uses to generate the QR-code. When the code is scanned, the user is brought to a webpage where they are asked to login if they aren't already. When the user logs in, the Pi receives a session token which it can use to submit scores on the player's behalf, and the Pi's identifier is connected to the user's account so they can press the online start button to start a game on their Pi.

![Login screen](/assets/images/{{ page.slug | slugify }}/login.png)

This project features a custom Java server back-end with SQL database, a Javascript-based front-end and a game programmed in Java (Processing 4). Features of the back-end include storing user accounts with securely hashed passwords, storing high-scores, admin accounts who can ban users and delete scores, requesting all user data, and managing Raspberry Pi identifiers and connections. A focus was placed on security, such as securing user passwords, securely handling user authentication, preventing users from executing actions they should not have access to and generally not trusting any input.

![Profile edit screen](/assets/images/{{ page.slug | slugify }}/profile.png)

My role in the project was primarily to develop the communication from the game on the Pi to the back-end, although I also helped with the Java back-end and Javascript front-end. This project gave me experience in interfacing with an API as well as developing the back-end, and was a good exercise in digital safety. The project was made together with 5 other students as part of my Computer Science pre-master. The code is available on [GitHub](https://github.com/Marro64/PlugNPi-Game).

![QR-code screen](/assets/images/{{ page.slug | slugify }}/qr-code.png)

![Start game](/assets/images/{{ page.slug | slugify }}/play.png)

![Leaderboard](/assets/images/{{ page.slug | slugify }}/leaderboard.png)