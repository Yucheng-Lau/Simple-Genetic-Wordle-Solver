# Wordle Genetic Algorithm Solver

This project implements a genetic algorithm–based solver for the popular game Wordle.
A population of candidate 5-letter words evolves over generations through selection, crossover, and mutation until it discovers the hidden target word.

# Features

* Fully functional Wordle game logic

* Evolutionary solver that:

      Scores guesses using Wordle-style feedback
    
      Selects top-performing parents
    
      Performs random genetic mutation
    
      Uses crossover to combine parent traits

* Adjustable population size & mutation rate

* Console-based generation-by-generation progress output

* Custom dictionary support

# Project Structure
├── wordleMain.py          # Entry point for the program

├── wordleQuestion.py      # Wordle game logic

├── wordleSolver.py        # Genetic algorithm solver

├── dictionary.txt         # List of valid 5-letter dictionary words

└── README.md

# How It Works

**WordleQuestion (Game Engine)**

1. Loads valid 5-letter words from dictionary.txt

2. Randomly selects a target word each run

3. Evaluates guesses using Wordle rules:

        correct → Right letter, right place

        present → Right letter, wrong place

        absent → Not in the word

**WordleGeneticSolver (Genetic Algorithm)**

1. Initialize a random population of valid words

2. Score fitness based on Wordle feedback

3. Select the top half of the population

4. Crossover random parents to produce offspring

5. Mutate letters with a configurable probability

6. Repeat until the solver finds the word

# Running the Program

1. Install Python

    Requires Python 3.8+.

2. Prepare dictionary

    Ensure dictionary.txt contains one 5-letter word per line.

3. Run the solver

    python3 wordleMain.py


You will see output similar to:

      Target word (hidden): crane
      Gen 1: Best guess = stare, Feedback = [...]
      Gen 2: Best guess = crate, Feedback = [...]
      ...
      ✅ Solved in 14 generations! Word was: crane

# Customization

You can adjust solver behavior in wordleSolver.py:

      solver = WordleGeneticSolver(
          game,
          population_size=200,
          mutation_rate=0.15
      )

# Dependencies

This project uses only Python’s standard library:

random

No external packages required.

# Example Input/Output

Dictionary Example (dictionary.txt):

      crane
      slate
      track
      sport
      ...


Sample Console Output:

      Gen 7: Best guess = crate, Feedback = ['correct','absent','present','correct','present']
      Gen 8: Best guess = crane, Feedback = ['correct','correct','correct','correct','correct']

# Limitations

Genetic algorithm may occasionally take many generations

Fitness scoring is simplistic but functional

No GUI (currently text-based)

# Contributing

Pull requests, feature suggestions, and improvements are welcome!
Ideas for expansion:

Smarter fitness functions

Visualization of evolution

Multi-run benchmarking

GUI / web interface
