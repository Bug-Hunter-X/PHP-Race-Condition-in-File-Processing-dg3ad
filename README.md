# PHP Race Condition in File Handling

This repository demonstrates a potential race condition in PHP code that involves concurrent file access.  The `bug.php` file shows the flawed code, while `bugSolution.php` provides a more robust solution.

## Problem

The `processFile` function in `bug.php` uses `flock()` for locking, but this isn't sufficient to guarantee atomicity in high-concurrency scenarios.  Simultaneous calls to `processFile` might lead to data corruption or unexpected behavior due to races.

## Solution

`bugSolution.php` addresses this by introducing a more robust locking mechanism using semaphores (or a similar approach depending on the context). This ensures that only one process can access the file at a time, preventing race conditions.

## Usage

1.  Clone this repository.
2.  Run `bug.php` and `bugSolution.php` separately to observe the difference in behavior (especially with multiple processes).