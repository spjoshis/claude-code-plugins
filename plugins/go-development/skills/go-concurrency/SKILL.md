---
name: go-concurrency
description: Master Go concurrency with goroutines, channels, select, sync primitives, and patterns for building concurrent applications.
---

# Go Concurrency Patterns

Master Go's concurrency model with goroutines, channels, and synchronization for building efficient concurrent systems.

## Core Patterns

### Goroutines
```go
func main() {
    go sayHello() // Launch goroutine

    time.Sleep(1 * time.Second) // Wait for goroutine
}

func sayHello() {
    fmt.Println("Hello from goroutine")
}
```

### Channels
```go
func main() {
    messages := make(chan string)

    go func() {
        messages <- "ping"
    }()

    msg := <-messages
    fmt.Println(msg)
}
```

### Worker Pool
```go
func worker(id int, jobs <-chan int, results chan<- int) {
    for j := range jobs {
        fmt.Println("worker", id, "processing job", j)
        time.Sleep(time.Second)
        results <- j * 2
    }
}

func main() {
    jobs := make(chan int, 100)
    results := make(chan int, 100)

    // Start workers
    for w := 1; w <= 3; w++ {
        go worker(w, jobs, results)
    }

    // Send jobs
    for j := 1; j <= 5; j++ {
        jobs <- j
    }
    close(jobs)

    // Collect results
    for a := 1; a <= 5; a++ {
        <-results
    }
}
```

### Select Statement
```go
select {
case msg1 := <-channel1:
    fmt.Println("Received", msg1)
case msg2 := <-channel2:
    fmt.Println("Received", msg2)
case <-time.After(1 * time.Second):
    fmt.Println("Timeout")
}
```

## Best Practices

1. Don't communicate by sharing memory; share memory by communicating
2. Close channels from sender side
3. Use buffered channels wisely
4. Handle goroutine cleanup
5. Use context for cancellation
6. Avoid goroutine leaks

## Resources
- https://go.dev/tour/concurrency/1
- https://go.dev/blog/pipelines
