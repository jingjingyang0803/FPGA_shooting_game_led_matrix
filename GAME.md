# FPGA Shooting Game on LED Matrix

A simple **FPGA-based shooting game** implemented in **VHDL**, designed to run on an FPGA board connected to a **Colorshield LED matrix**.

The player controls a gun that shoots bullets at an alien moving across the screen. 

The game demonstrates digital design concepts such as **modular architecture, state machines, and hardware debugging using simulation**.

# Game features

**1. Alien health states and visual feedback**

The alien now has multiple health states instead of being defeated with a single hit.

At the start of the game, the alien is green, representing full health. After the first hit it turns yellow, and after the second hit it turns red.

After the third hit, the alien disappears and the player wins the game. The color change provides clear visual feedback about the alien’s remaining health.

**2. Offensive alien**

The alien is made offensive by descending one row each time it reaches the horizontal edge of the screen.

This creates constant pressure for the player because the alien gradually moves closer to the gun. As a result, each round becomes very fast and intense, making the gameplay more challenging.

**3. Lose condition and lose effect**

A lose condition is added when the alien descends too low. If the alien reaches the same row as the gun tip, the player loses the game.

When this happens, a lose symbol is displayed on the LED matrix: two diagonal parallel red lines, indicating the failure state.

**4. Dynamic victory effect**

The original victory effect is a static big red heart (40 pixels).

In our improved version, the victory animation becomes dynamic: a line moves left and right while its color cycles through the seven rainbow colors.

This makes the victory screen more vivid and visually appealing compared to the static effect.

# Hardware

The project is designed for an FPGA board connected to a **Colorshield LED matrix display**.

Main hardware components:

- FPGA development board
- Colorshield LED matrix
- Push button input (shooting)
- Switch input(restarting)

The LED matrix is driven through a **serial transmitter and write sequencer**, which update pixel data stored in a register bank.

# Bitstream Versions

This folder contains several compiled FPGA versions created during development.

| File | Description |
| --- | --- |
| `v1_game_top_static.bit` | Early version of the game with basic functionality |
| `v2_game_top.bit` | Improved gameplay logic |
| `v3_improved_game_top.bit` | Version including alien health system |
| `v4_improved_game_top_blinky.bit` | Final improved version with additional visual effects |

These bitstreams can be programmed using **Vivado Hardware Manager** directly **without rebuilding the design**.

# How the System Works

The design is built from multiple hardware modules.

Simulation with **testbenches and waveform analysis** was used extensively during development to verify correct behavior.

# Possible Future Improvements

Potential extensions for the project:

- Adjustable alien speed
- Multiple aliens
- Score system
- More complex animations and visual effects
