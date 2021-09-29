# Game of Life

## Problem Description

(Borrowed from [codingdojo.org](https://codingdojo.org/kata/GameOfLife/).)

This exercise is about calculating the next generation of Conway’s game of life, given any starting position. See [Wikipedia](http://en.wikipedia.org/wiki/Conway%27s_Game_of_Life) for background information.

We begin with a two dimensional grid of cells, where each cell is either alive or dead. In this version of the problem, the grid is finite, and no life can exist beyond the edges. When calcuating the next generation of the grid, follow these rules:

1. Any live cell with fewer than two live neighbours becomes dead (as if caused by underpopulation).
2. Any live cell with more than three live neighbours becomes dead (as if by overcrowding).
3. Any live cell with two or three live neighbours remains live in the next generation.
4. Any dead cell with exactly three live neighbours becomes a live cell.

You should write a program that can accept an arbitrary grid of cells, and will output a similar grid showing the next generation.

### Clues

One option could be to parse input like the following:

```
4 8
........
....*...
...**...
........
```

(Where 4 is the number of rows and 8 is the number of columns.)

The output could then be something like:

```
........
...**...
...**...
........
```

However, it could also be completely acceptable to have an API like this:

```python
gameboard = GameOfLife([(1, 4), (2, 3), (2, 4)])
gameboard.tick() # `tick` moves the game to the next state
gameboard.livecells() # [(1, 3), (1, 4), (2, 3), (2, 4)]
```