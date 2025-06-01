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

