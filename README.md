# 🤖 Tic-Tac-Toe Reinforcement Learning Agent

This project implements a **Tic-Tac-Toe game** where an AI agent learns to play using **Reinforcement Learning (Q-Learning)**.  
The agent improves its gameplay by playing thousands of games against a random opponent, learning which moves lead to winning outcomes.

---

## 🧠 Project Overview

- **Goal:** Train an agent to play Tic-Tac-Toe intelligently using **Q-Learning**.
- **Learning Method:** The agent uses rewards (+1 for win, -1 for loss, 0 otherwise) to update a Q-table.
- **Environment:** Simple 3x3 Tic-Tac-Toe board.
- **Opponent:** Randomly plays available moves.

---

## 🏗️ How It Works

1. **Environment (`TicTacToe` class):**
   - Manages the 3x3 board, current player, and game logic.
   - Checks for valid moves and winners.
   - Returns rewards based on game outcomes.

2. **Agent (`QLearningAgent` class):**
   - Stores experience in a Q-table as `(state, action)` pairs.
   - Uses the **epsilon-greedy** strategy:
     - With probability ε (epsilon), it explores random moves.
     - With probability (1−ε), it exploits the best-known move.
   - Updates Q-values based on rewards and future expected values.

3. **Training Loop:**
   - The agent plays multiple games (episodes) against a random opponent.
   - It updates its Q-table after every move based on feedback.
   - Over time, it learns to play optimally.

---

## 🧩 Q-Learning Formula

The agent updates its Q-values using the rule:

\[
Q(s,a) = Q(s,a) + \alpha \times [r + \gamma \times \max Q(s',a') - Q(s,a)]
\]

Where:
- \( \alpha \): Learning rate  
- \( \gamma \): Discount factor  
- \( r \): Reward received  
- \( s \): Current state  
- \( s' \): Next state  
- \( a \): Action taken

---

