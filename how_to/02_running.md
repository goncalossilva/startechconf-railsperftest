!SLIDE

## Running the tests

!SLIDE

### Benchmarking

    @@@ ruby
    $ rake test:benchmark

!SLIDE

### Benchmarking

    @@@ ruby
    UserTest#test_homepage (718 ms warmup)
               wall_time: 150 ms
                  memory: 7.8 MB
                 objects: 85,188
                 gc_runs: 0
                 gc_time: 0 ms
    
    UserTest#test_creation (179 ms warmup)
               wall_time: 176 ms
                  memory: 10 MB
                 objects: 122,823
                 gc_runs: 0
                 gc_time: 0 ms

!SLIDE

### Profiling

    @@@ ruby
    $ rake test:profile

!SLIDE

### Profiling

    @@@ ruby
    UserTest#test_homepage (694 ms warmup)
        process_time: 501 ms
              memory: 24 KB
             objects: 308,614
    
    UserTest#test_creation (161 ms warmup)
        process_time: 555 ms
              memory: 27 KB
             objects: 343,484

!SLIDE

### Profiling

    @@@ ruby
    UserTest#test_homepage_memory_flat.txt
    UserTest#test_homepage_memory_graph.html
    UserTest#test_homepage_memory_stack.html
    UserTest#test_homepage_memory_tree.txt
    UserTest#test_homepage_objects_flat.txt
    UserTest#test_homepage_objects_graph.html
    UserTest#test_homepage_objects_stack.html
    UserTest#test_homepage_objects_tree.txt
    UserTest#test_homepage_process_time_flat.txt
    UserTest#test_homepage_process_time_graph.html
    UserTest#test_homepage_process_time_stack.html
    UserTest#test_homepage_process_time_tree.txt

!SLIDE

## Quick testing

!SLIDE

### Benchmarking

    @@@ ruby
    $ rails benchmarker "Ruby.expensive_method"

!SLIDE

### Profiling

    @@@ ruby
    $ rails profiler "Ruby.method; Ruby.another_method"

!SLIDE

## Configurability

!SLIDE

### Runs, output formats, metrics
