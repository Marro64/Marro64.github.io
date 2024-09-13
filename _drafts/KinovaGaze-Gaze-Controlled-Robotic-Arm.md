---
layout: post
title: "Bachelor Thesis: KinovaGaze Gaze Controlled Robotic Arm"
---

I recently graduated my bachelor Creative Technology with my bachelor thesis titled "Design of an Eye-Gaze Interface for Controlling an Assistive Robot Arm". In my thesis, I describe the creation and testing of the KinovaGaze system, a system for controlling a Kinova assistive robotic arm using gaze.

![Testing session with Andrei](/assets/images/{{ page.slug | slugify }}/testing-with-andrei.jpg)

The system was created for [Ability Tech](https://abilitytech.nl/), an organisation creating technology for helping people with disabilities live a better life. Their main client, Andrei, is severely impaired in his ability to move. KinovaGaze intends to provide him with more freedom by allowing to use the limited motor functions he has control over, namely his eyes, to physically interact with the world around him. It is built upon the prior work by Damian Gaethofs at Ability Tech, who created a proof-of-concept system for his bachelor thesis. My thesis extended his work with a more fully formed system and testing with Andrei and other participants beyond the author.

![Ability Tech website homepage](/assets/images/{{ page.slug | slugify }}/ability-tech.jpg)

By using a Tobii gaze-tracker and configuring it to always move the cursor to the position the user is looking, a web-interface is controlled using hover-activated buttons with a webcam feed to move a Kinova assistive robotic arm. Users are given full 3-axis control over the arm, as well as being able to open and close the hand. Rotation has not been implemented. 

The main user interface has buttons at the top for locking the interface, recentering the arm and switching between 2-axis control and z-axis/hand control. Two versions of the interface were made, one where the arm keeps moving after the user has confirmed a direction until a stop button gets hit, and one where confirming a direction is easier but movement stops when the user looks away.

![Screenshot of hold interface](/assets/images/{{ page.slug | slugify }}/hold-interface.jpg)

The system is implemented on a Raspberry Pi which connects via Ethernet to the user's computer and opens a web-ui on the local network. The user is expected to have a gaze-tracker connected to their computer. The Raspberry Pi is connected via USB to a Kinova robotic arm and a webcam.

The custom web-ui is programmed in JavaScript using the P5.js library for graphical functions and includes a custom toolkit for hover-activated buttons. It sends commands to a custom ROS node written in Python which processes them and sends commands to the Kinova arm via the Kinova-ROS stack. A Flask HTTP server written in Python hosts the web interface, including streaming a camera feed over the local network. A DHCP server ensures that the local network is setup and available when the Pi is connected to a computer. Finally, Systemd services are used to start all processes including the rosbridge server and Kinova-ROS stack on boot.

![Diagram of the software and hardware of KinovaGaze](/assets/images/{{ page.slug | slugify }}/system-diagram.png)

Testing was performed with multiple users to test the system and compare the interfaces. A controlled setup was made where the participant would pick up and put down a bottle in marked positions. Time taken and user feedback via a questionnaire and a discussion were recorded, as well as a recording of the interface during use. The results showed that some points of improvement are the usefullness of the webcam and the ability to stop in a precise place. The users also found it difficult to learn which buttons moved in which axis.

![Bar diagram of questionnaire results](/assets/images/{{ page.slug | slugify }}/post-questionnaire-total.png)

Testing with Andrei was also performed. Here it became clear that it was difficult for Andrei to understand the control of the arm. This may be because of deficiencies in the design and implementation of the interface, but it could also have to do with his lack of experience controlling objects in 3-dimensional space. A simpler interface was recommended for future work, one where the user tells the arm what it wants to accomplish and where the system then figures out the movements it needs to make to accomplish this. 

![Testing session with Andrei](/assets/images/{{ page.slug | slugify }}/testing-with-andrei-alt.jpg)

This bachelor thesis taught me even more the importance of getting customers involved early and deeply. I was under the misunderstanding that the prior work had already tested with Andrei, but this was not the case and resulted in a system which he did not work well for him despite working decently for others. However, now that we know how he responded to this system, we can work to further improve the system in a direction which he can better use, and this system already lays a good foundation to build upon. During this project I learned about working with ROS as well as JavaScript, two systems I had very little to no experience with prior to this project. I also learned how to manage a project by myself when most prior projects at my study were done in a larger group where I focussed on technical work while delegating a lot of planning and writing tasks to other members. 

The [code and documentation](https://github.com/abilitytechlab/KinovaGaze) to this project is available on GitHub. Writing the documentation was an exercise in trying to imagine what a future contributor would want to know when learning the project, and it includes a lot of knowledge which took me a long time to figure out. I hope to continue working with Ability Tech to improve the system, but anyone else could also continue using everything provided there. Furthermore, the [full report](https://essay.utwente.nl/101954/) is available on the UTwente repository and provides more information on the background, research done, choises made, testing results and recommendations for future work.

![A picture of the testing setup](/assets/images/{{ page.slug | slugify }}/testing-setup.jpg)
