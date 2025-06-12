---
title: "Magic Chessboard"
author: "Tejas Panicker"
description: "A  chessboard that automatically detects piece movement by a human player and calculates the best move to play, and then moves the pieces to execute."
created_at: "2024-05-31"
---

– 5/31 Planning and Kickoff!

Today, we started fully planning the layout for the chessboard.
We planned how we were going to package our components in order to keep a small size relative to the board.
The plan is to create a sort of layered system in which different components exists in rough layers beneath the board.
This minimizes interference between them, especially since we have a compact gantry, and allows us to package everything better.
We wanted to avoid having a lot of extra space on the sides because it looks ugly and ruins the vibe.

Our current plan is (from top to bottom):
Thin wooden board and custom-sized pieces with magnet bases
Currently decided on 4cm x 4cm 
PCB with built-in Hall Effect sensors to read the squares
Core XY gantry to house an electromagnet carriage
Decided currently on 1010 extrusions to house mgn7c rails
![image (3)](https://github.com/user-attachments/assets/c107bafa-8ef4-455c-9d28-f59db6970be6)
To the side, we are going to house an ESP32 and Raspberry Pi 02W for the chess engine
Preferably within the margins of the board, which also has the motors, to reduce the frame size

We also created a preliminary parts list of all the parts we may need, excluding certain hardware that depends on the scaling we decide upon.
	These parts largely include components that will stay pretty much fixed such as sensors and boards, as well as motors to an extend.

We also created an initial rough CAD of the board in Onshape to visualize what margin we will need on the side, as well as positioning of our rails and motors to reduce form factor. 
![Screenshot 2025-05-31 215319](https://github.com/user-attachments/assets/65af8d03-da3e-41c6-9729-6ee79b1ade44)

The plan now is to design a gantry to the dimensions of our board and prepare to mount the electromagnet to it while also continuing to plan out parts and ensure compatibility. Additionally, we plan to start designing the PCB to hold the hall effect sensors.

Time Spent this session: 2.5 hours

– 6/11/25

Today, we created a basic gantry model using the parts we decided upon last session. The gantry is placed above a model of our chessboard with proper dimensions, but in reality, it will be below. The gantry features 1020 extrusion and 350mm MGN7 rails. We created a custom cross-mount that allows us to connect perpendicular MGN7 rails. 
We found that if we keep both rails facing upward, the gantry becomes very tall, and we wanted the board to have the lowest profile possible to make the experience better. To solve this issue, we tried to make one of the MGN7 rails face downward to make the gantry partially fold in on itself. 
However, because we had to have long arms that extend outward from the contact point between rails, the carriage would hit our mounting before reaching the end, which would limit our reach. To fix this issue, we put the mounting arm above the rail, which had the added benefit of making our gantry even more compact. 
![Screenshot 2025-06-11 213002](https://github.com/user-attachments/assets/a0f5ee38-b65b-41e3-a5d8-1e72735d426b)
![Screenshot 2025-06-11 213033](https://github.com/user-attachments/assets/47ff6b72-511d-4862-816e-5c8067cac623)

Note that the cross brace will be 3d printed, and thus needs to be very thick in order to withstand the force applied.

We also started working on a mount that will attach to the middle carriage and hold our electromagnet.
The current changes that need to be made to this model are adding points to route and pinch the belts to create the CoreXY belting pattern and finishing the magnet mount. We also need to include the stepper motors at the ends after the belt mounting has been completed.
	
Another significant part of this project we worked on was the PCB that will hold the Hall Effect sensors. We imported the board and its dimensions into EasyEDA and started setting up components. We first made the schematic using specifications we found online to ensure the proper voltage and connection. We set up all 64 sensors, as well as their multiplexing boards and capacitors.
![Screenshot_2025-06-11_at_5 07 02_PM](https://github.com/user-attachments/assets/bb4f6d03-0fde-4a8e-b677-bdc3c05b245e)
After we had set up the schematic, we started working on laying out the components and their traces. This, unfortunately, is a very slow process because the components are not in a perfect order, and they need to be placed manually into each square, along with their capacitor. So far, we have completed 16 squares and will work further.
![Screenshot_2025-06-11_at_9 17 17_PM](https://github.com/user-attachments/assets/8120955f-17c4-4ddf-b13f-1547f5a4f806)
Some additional things that we did were we continued to check out compatibility, especially with voltage, because it has become difficult to keep track of. Our ESP32 uses 3.3V, our Raspberry Pi 5V, but our battery will be a 2S LiPO, which is 7.4V. To make things a little easier, we are trying to use a 5V electromagnet and feed 7.4V directly to the stepper motors. We ensured we had the parts to manage this system as well as that everything was at proper specifications to avoid destroying anything.

Time spent on this session: 3 hours
