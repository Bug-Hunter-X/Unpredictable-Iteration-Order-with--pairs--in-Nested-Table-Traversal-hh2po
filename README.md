# Lua Nested Table Traversal Bug

This repository demonstrates a potential issue with Lua's `pairs` iterator when traversing nested tables.  The `pairs` function does not guarantee a specific iteration order, which can lead to unpredictable results if the order of elements is significant.

## The Bug

The `bug.lua` file contains a function `foo` that recursively traverses a nested table.  However, because `pairs` doesn't guarantee iteration order, the order in which the nested tables are processed might vary between Lua implementations or even different runs of the same code.

## The Solution

The `bugSolution.lua` file provides a solution that uses a different approach to ensure a consistent iteration order, such as sorting the keys before iteration.

## How to reproduce the bug

1. Clone this repository.
2. Run `bug.lua` using a Lua interpreter.
3. Observe the order of output. Run it multiple times to see variations in output.
4. Compare to the deterministic results from `bugSolution.lua`