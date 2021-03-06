![Functional tests](https://github.com/dassencio/sudoku/workflows/Functional%20tests/badge.svg)
![Static code analysis](https://github.com/dassencio/sudoku/workflows/Static%20code%20analysis/badge.svg)

# Description

A Sudoku puzzle solver (written in Python 3) which models and solves the puzzle
as an [integer linear programming](https://diego.assencio.com/?index=25ea1e49ca59de51b4ef6885dcc3ee3b)
(ILP) problem.

# License

All code from this project is licensed under the GPLv3. See the
[`LICENSE`](https://github.com/dassencio/sudoku/tree/master/LICENSE)
file for more information.

# Required modules

The `pulp` module is used. You can install it with the following command:

    pip3 install pulp==2.1

# Usage instructions

This projects illustrates how a Sudoku puzzle can be formulated as an integer
linear programming problem. It contains two main files:

- `sudoku.py`: a self-contained module with all the functionality needed to
  define and solve a puzzle
- `sudoku-solver`: an executable script which exemplifies how `sudoku.py` can
  be used to solve a puzzle.

By default, `sudoku-solver` takes its input from `stdin` and outputs the solved
puzzle on `stdout`. To solve a Sudoku puzzle, run `./sudoku-solver` and provide
the following:

- number of rows and columns on each puzzle block in one line (e.g. `2 3`)
- for each puzzle row, a line such as `_ _ _ 4 5 _` specifying the initial
  state of the row; initially unknown values can be represented using any
  non-integer character or string (e.g. `_`, `__`, `?` or `*`)

As an example, the following input specifies a puzzle with 2×3 blocks, i.e.,
each block contains 2 rows and 3 columns, and the puzzle contains 6 rows/columns
in total:

    2 3
    _ _ _ 2 _ _
    _ _ _ 4 5 _
    _ 3 4 _ _ _
    _ _ _ 1 4 _
    _ 6 1 _ _ _
    _ _ 5 _ _ _

The output is the solution to the puzzle:

    5 4 6 2 3 1
    2 1 3 4 5 6
    1 3 4 5 6 2
    6 5 2 1 4 3
    4 6 1 3 2 5
    3 2 5 6 1 4

# Running the functional tests

This repository comes with tests which can be used to validate the solver. These
tests also illustrate the input format discussed above.

Each test contains an associated input file (e.g. `test05.in`) which defines the
puzzle, and an associated output file (e.g. `test05.out`) which specifies the
expected output contaning the solution to the puzzle. These files are located
in the `tests` subdirectory. You can execute all these tests by running the
`run-tests` script:

    ./run-tests

# Contributors & contact information

Diego Assencio / diego@assencio.com
