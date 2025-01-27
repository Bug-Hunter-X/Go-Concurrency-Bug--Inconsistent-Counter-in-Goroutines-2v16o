# Go Concurrency Bug: Inconsistent Counter in Goroutines

This repository demonstrates a common concurrency bug in Go where the use of goroutines without proper synchronization leads to an inconsistent count.

## Bug Description

The `bug.go` file contains a program that launches 1000 goroutines, each incrementing a shared counter.  Without proper synchronization mechanisms, the final count is often incorrect due to race conditions.  Each goroutine's attempt to increment the counter can be interrupted, resulting in lost increments.

## Solution

The `bugSolution.go` file provides a corrected version of the program using a mutex to protect the shared counter. This prevents race conditions and ensures that the final count is accurate.

## How to Run

1. Clone this repository.
2. Navigate to the repository's directory.
3. Run the buggy code using `go run bug.go`.
4. Run the corrected code using `go run bugSolution.go`.

Observe the difference in output. The buggy version will often produce a count significantly less than 1000, while the solution will always produce 1000.
