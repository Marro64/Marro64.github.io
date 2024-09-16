---
layout: post
title: Ducks 'n Explosions
---

Ducks 'n Explosions is a game made by me and Tjeerd Verscheuren in a few weeks as the final assingment in the Interactive Media module. It is a game made in Unity when you throw bombs at a duck to guide it towards exiting a school it somehow got locked inside. The duck is explosion-proof, so don't worry about his safety. However he is also not very smart, and does not much more than run away from explosions. He'll pick up any item he runs over, and he'll drop it if he gets caught in an explosion. The exit is locked and there's a guard in the way who will scare away the duck, so you'll have to think outside the box to manage an escape.

The game is available on [itch.io](https://marro64.itch.io/ducks-n-explosions) (play online here!)

```
"While looking for food and leftovers,
    a duck got lost and stuck inside a school…

       Use explosions to guide him outside of the school,
          back to the pond."
```

![Screenshot of the game](/assets/images/{{ page.slug | slugify }}/screenshot-1.png)

My main responsibility was the code, while Tjeerd made the assets and school layout. The code was written in C# as is the norm for [Unity](https://unity.com/), the graphics were made in [Blender](https://www.blender.org/) and the sound was implemented using [FMOD](https://www.fmod.com/) as required by the assignment.

The main concept of the game was inspired by games where you do not have direct control of a physical character, but must accomplish goals indirectly,such as *Lemmings*, newer *Mario Vs. Donkey Kong* games or *Ghost Trick*. It is a puzzle game where you have to search for tools in the surroundings to accomplish your goal. The main difficulty comes from the control scheme, as it would be a trivially easy game otherwise. The game is also designed to not need an explicit tutorial, starting in a simple tutorial area where players can hopefully discover the workings of the game through trial-and-error.

A major feature of the game is that just about everything is explodable, and there are multiple rooms who's only purpose is to be a sandbox for explosions. This is based in the idea that a game has to be enjoyable even without an objective to be truly fun for the player.

![Screenshot of the editor](/assets/images/{{ page.slug | slugify }}/screenshot-editor.png)

Since the game was made in only a few weeks with other courses taking up time, it is rough around the edges. With more time I'd have added a hint as to how to deal with the guard and camera transitions to indicate when an important event happens. I'd have made the control of the duck less frustrating through more iteration and a smarter AI, starting with a system where it responds to a bomb while it is still flying towards him.

What I am happy with is the camera system. Its rotation always follows the duck, and its position is dynamic depending on where the duck is. If the duck is in a room, the camera is positioned on a static point. If the duck is in a hall, the camera goes on a track and follows the duck, switching between tracks if the duck enters a different hall. The camera is at an angle to allow the player to better see the sides of walls and objects, but this means that walls might block your view of the duck and prevent you from throwing bombs where you want to. Therefore walls dynamically become translucent and intangible to bombs depending on where the camera is, ensuring they don't get in the way.