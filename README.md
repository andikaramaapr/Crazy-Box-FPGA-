# Crazy Box — FPGA-Based Endless Runner Game

## Overview

**Crazy Box** is a simple endless runner game developed using the Xilinx Spartan-3E Starter Board and VHDL. The game displays a player-controlled box and moving obstacles on a monitor through a VGA connection.

The objective is to avoid incoming obstacles and the upper and lower boundaries for as long as possible. Players can move the box vertically and select between Easy and Hard difficulty modes using the physical buttons and switches on the FPGA board.

## Features

- **FPGA-Based Game Logic** — Implements game behavior using VHDL on the Xilinx Spartan-3E platform.
- **VGA Display Output** — Renders the game directly on an external monitor.
- **Vertical Player Movement** — Controls the player box using onboard push buttons.
- **Two Difficulty Modes** — Selects Easy or Hard mode using a board switch.
- **Start and Pause Controls** — Starts or pauses gameplay through a physical switch.
- **Obstacle Collision Detection** — Ends the game when the player collides with an obstacle.
- **Boundary Detection** — Triggers Game Over when the player reaches the upper or lower boundary.

## Gameplay

The game consists of a red player box, six moving black obstacles, and cyan upper and lower boundaries.

The player must avoid the incoming obstacles while staying within the playable area. The obstacles move toward the player's position, and their movement speed varies according to the selected difficulty mode.

When a collision occurs, the game stops and displays **GAME OVER** on the monitor.

<!-- Add a gameplay screenshot here -->
<!-- ![Crazy Box Gameplay](images/gameplay.png) -->

## Hardware Requirements

| Component | Purpose |
|---|---|
| Xilinx Spartan-3E Starter Board | Executes the game logic |
| VGA-compatible monitor | Displays the game |
| VGA cable | Connects the FPGA board to the monitor |
| Onboard push buttons | Controls vertical player movement |
| Onboard switches | Controls game state and difficulty |

## Software and Technologies

- VHDL (VHSIC Hardware Description Language)
- Xilinx ISE
- PlanAhead for I/O pin assignment
- User Constraint File (UCF)
- VGA synchronization and RGB output signals

## System Architecture

The system is organized into three main blocks:

1. **Input** — Receives the onboard clock, push-button inputs, and switch states.
2. **Processing** — Executes the game logic, player movement, obstacle movement, collision detection, and display rendering on the FPGA.
3. **Output** — Generates VGA RGB signals and horizontal and vertical synchronization signals for the monitor.

<!-- Add the block diagram from Figure 3.1 -->
<!-- ![System Block Diagram](images/system-block-diagram.png) -->

## Controls

| Input | Function |
|---|---|
| Switch 0 | Start or pause the game |
| Switch 3 | Select Easy or Hard mode |
| North push button | Move the player vertically |
| South push button | Move the player vertically |

The switch settings allow the difficulty to be selected while the game is idle or paused. In Hard mode, obstacles move faster than in Easy mode.

## Implementation

The development process consists of the following stages:

1. Create the VHDL project and define its input and output ports.
2. Implement the game logic and VGA signal generation.
3. Assign FPGA pins through the User Constraint File.
4. Run syntax checking, synthesis, translation, mapping, and routing in the Xilinx development environment.
5. Generate the programming file and configure the Spartan-3E board.
6. Connect the board to a VGA monitor and test the game controls and collision behavior.

### VGA Output

The design generates RGB color signals along with horizontal synchronization (`HSYNC`) and vertical synchronization (`VSYNC`) signals. These outputs are connected to the monitor through the board's VGA interface.

### Game Logic

The game logic manages the player position, six obstacle positions, difficulty selection, and collision conditions. The player can move vertically while the obstacles travel toward the player's side of the screen.

When a collision with an obstacle or either boundary is detected, the game enters its Game Over state.

## Testing and Results

The project was programmed onto the Xilinx Spartan-3E Starter Board and tested using an external monitor.

The reported implementation demonstrates:

- Game graphics displayed through VGA.
- Player movement using onboard push buttons.
- Start and pause behavior through a switch.
- Easy and Hard difficulty selection.
- Obstacle movement and collision-triggered Game Over behavior.

<!-- Add the test result photograph from Figure 4.2 -->
<!-- ![Gameplay Test](images/gameplay-test.png) -->

## Project Images

Use the following images from the report if you want to document the implementation visually.

<!-- Add the physical system photograph from Figure 4.3 -->
<!-- ![Physical System](images/physical-system.jpg) -->

<!-- Add the input/output design from Figure 3.2 -->
<!-- ![Input and Output Design](images/io-design.png) -->

<!-- Add the flowchart from Figure 4.1 -->
<!-- ![Game Flowchart](images/game-flowchart.png) -->

## Limitations and Future Improvements

The current implementation focuses on basic endless runner mechanics. Possible future improvements include:

- Adding a score counter and high-score tracking.
- Introducing power-ups and additional obstacle patterns.
- Improving the game's graphics and animations.
- Adding more gameplay modes and mechanics.

## Project Context

This project was developed as a final assignment for the FPGA Programming course in the Computer Engineering program at Universitas Brawijaya.

**Platform:** Xilinx Spartan-3E Starter Board  
**Language:** VHDL  
**Display Interface:** VGA  
**Game Genre:** Endless Runner
