# Tetris Game using Verilog

## Description

Tetris is a classic block-based game implemented using Verilog HDL. The game controls falling blocks inside a grid and allows the player to move the active block left or right while it falls.

This project demonstrates sequential logic, counters, collision detection, position control, and game-state management using Verilog.

## Features

* 10-column game grid
* 20-row game area
* Falling block control
* Left and right movement
* Automatic downward movement
* Boundary detection
* Collision detection
* Game-over detection
* Reset functionality
* Simulation-ready design

## Inputs

| Signal       | Description              |
| ------------ | ------------------------ |
| `clk`        | System clock             |
| `reset`      | Resets the game          |
| `move_left`  | Moves the block left     |
| `move_right` | Moves the block right    |
| `drop`       | Moves the block downward |

## Outputs

| Signal      | Description                       |
| ----------- | --------------------------------- |
| `block_x`   | Horizontal position of the block  |
| `block_y`   | Vertical position of the block    |
| `game_over` | Indicates that the game has ended |

## Game Grid

The game uses a 10 × 20 grid:

```text
+--------------------+
|                    |
|       BLOCK        |
|                    |
|                    |
|                    |
|                    |
|                    |
|                    |
|                    |
|                    |
|                    |
|                    |
|                    |
|                    |
|                    |
|                    |
|                    |
|                    |
|                    |
|                    |
+--------------------+
       10 columns
```

## Working Principle

1. After reset, the block is positioned at the top-center of the grid.
2. The block automatically moves downward on every clock cycle.
3. `move_left` and `move_right` control horizontal movement.
4. The block cannot move outside the game boundary.
5. When the block reaches the bottom of the grid, it stops.
6. A new block can then be generated.
7. If the available space is full, the `game_over` signal becomes HIGH.

## Main Components

### Block Controller

Controls the current block position.

### Movement Controller

Handles left, right, and downward movement.

### Collision Detection

Prevents the block from moving outside the game area.

### Game State Controller

Controls reset, active play, and game-over conditions.

## Simulation

The testbench generates a clock and applies different player controls.

Example:

```text
Reset → Block starts at (5,0)
Move Left → Block moves to (4,0)
Move Right → Block moves to (5,0)
Drop → Block moves downward
```

## Applications

* FPGA game development
* Digital logic learning
* FSM design
* Hardware-based gaming
* Verilog HDL practice
* Real-time control systems

## Tools Required

* Verilog HDL
* Icarus Verilog
* ModelSim / QuestaSim
* Xilinx Vivado (optional)
* GTKWave for waveform visualization

## Project Files

```text
src/tetris_game.v
```

Main Tetris game controller.

```text
testbench/tetris_game_tb.v
```

Testbench for functional verification.

```text
simulation/expected_output.txt
```

Expected simulation results.

## Future Improvements

The project can be extended with:

* Multiple Tetris block shapes
* Block rotation
* Line clearing
* Score counter
* Level control
* VGA display
* Keyboard or button interface
* Seven-segment score display

## Author

Created as a Verilog HDL FPGA project for GitHub and digital design learning.
