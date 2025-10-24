# 🧬 Genetic Algorithm for the Knapsack Problem

This project implements a **Genetic Algorithm (GA)** to solve a variation of the **Knapsack problem**.  
Each individual in the population represents a possible combination of magical items that can be placed in a knapsack with a maximum weight capacity.

---

## 📋 Problem Description

The goal is to **maximize the total profit (gain)** while keeping the total weight of the items **below the knapsack limit**.

### Items
| Item | Gain | Weight | Restriction |
|------|-------|---------|-------------|
| Decoy detonators | 10 | 4 | — |
| Love potion | 8 | 2 | Min: 3 units |
| Extendable ears | 12 | 5 | — |
| Skiving snackbox | 6 | 5 | Min: 2 units |
| Fever fudge | 3 | 2 | — |
| Puking pastilles | 2 | 1.5 | — |
| Nosebleed nougat | 2 | 1 | — |

Maximum knapsack weight: **30 units**

---

## ⚙️ Algorithm Overview

The algorithm follows the traditional structure of a Genetic Algorithm:

1. **Initialization**  
   A random population of individuals is generated. Each individual represents a possible solution (a list of item quantities).

2. **Fitness Evaluation**  
   The fitness of each individual is computed as the total profit of all selected items, normalized across the population.

3. **Selection (Roulette Wheel)**  
   Parents are selected based on their fitness probabilities.

4. **Crossover (Uniform Crossover)**  
   Parents are crossed with a probability `probabilidad_cruza` using uniform crossover (`cruza_uniforme` defines how genes are mixed).

5. **Mutation**  
   Genes of the offspring are mutated with a probability `probabilidad_mutacion`.

6. **Replacement**  
   The best individuals between parents and children are kept in the next generation.

7. **Iteration**  
   Steps 2–6 are repeated for a fixed number of generations.

---

## 🧩 Key Parameters

| Parameter | Description | Default Value |
|------------|--------------|----------------|
| `numero_poblacion` | Number of individuals in the population | 10 |
| `generaciones` | Number of generations to evolve | 50 |
| `peso_mochila` | Maximum knapsack weight | 30 |
| `probabilidad_cruza` | Probability of crossover | 0.85 |
| `probabilidad_mutacion` | Probability of mutation | 0.1 |
| `cruza_uniforme` | Uniform crossover threshold | 0.5 |

---

## 📈 Fitness Function

The fitness of each individual is calculated as:

\[
\text{fitness}(i) = \frac{\text{gain}(i)}{\sum_{j=1}^{N} \text{gain}(j)}
\]

Where `gain(i)` is the total profit of individual *i*.

Invalid individuals (those exceeding the knapsack’s weight limit) are discarded or regenerated.

---

## 🧮 File Structure

├── main.py # Main file with the genetic algorithm implementation

├── README.md # Documentation (this file)


---

## 🚀 How to Run

### 1️⃣ Requirements
- Python 3.x
- Libraries: only built-in `random`

### 2️⃣ Execution
Run the program with:
```bash
python main.py
