# Gomoku (2022 IP2 Project 3)

A strategic **Gomoku (Five-in-a-Row)** artificial intelligence built for a 15x15 board. This project focuses on implementing efficient tree search algorithms and board evaluation heuristics to defeat various baselines.



## Strategy & Algorithms

To achieve high performance and competitive rankings, the implements the following technical features:

### 1. Minimax Algorithm
* **Role**: Core Search Engine.
* **Ability**: Simulates multiple turns ahead by assuming both players play optimally. It explores the game tree to find the move that maximizes the algorithm's advantage while minimizing the opponent's.

### 2. Alpha-Beta Pruning
* **Role**: Search Optimization.
* **Ability**: Drastically reduces the number of nodes evaluated in the search tree. By "pruning" branches that cannot possibly influence the final decision, the algorithm can search significantly deeper within the 10-second time limit.

### 3. State Value Function (Heuristics)
* **Role**: Board Evaluation.
* **Ability**: A custom scoring system that assigns values to specific patterns (e.g., "Live Three," "Blocked Four," or "Five in a Row"). This allows the algorithm to quantify how "good" a board position is without reaching the end of the game.



## Technical Setup

* **Language**: C++
* **Compiler**: g++
* **Environment**: Linux / WSL (Ubuntu 20.04+)



## Project Structure

* `src/`:
    * `main.cpp`: The **Game Engine**. It initializes the board, calls players in turn, manages the 10-second time limit, and determines the winner.
    * `player.cpp`: **My Main Player**. This is my primary brain containing the Minimax algorithm, Alpha-Beta pruning, and your custom evaluation function.
* `baseline/`: A **Baseline AI**. It serves as a testing opponent to verify my environment and basic logic.



## How to Build & Run

   ```bash
    cd src

    make

    ./main ./player ../baselines/linux/baseline1

    ./main ../baselines/linux/baseline1 ./player

    ./main ./player ../baselines/linux/baseline2

    ./main ../baselines/linux/baseline2 ./player