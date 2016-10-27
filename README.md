# Garbage Collector

My task was to implement a garbage collector for a basic Scheme interpreter implemented in C.
All the files here were already complete except *alloc.c*, which was where I completed the
implementation of the function *collect_garbage()*. More details below.

This garbage collection was done in a mark-and-sweep way. For the marking phase, I implemented 
the functions *mark_environment(Environment \*env), mark_value(Value \*v),* and *mark_lambda(Lambda \*f).*
These functions recursively call each other to handle various relationships between the data structures.
*mark_eval_stack* was also implemented to handle the evaluation stack.

Next is the sweep phase. Three helper functions were created for this phase. They are
*sweep_values(), sweep_lambdas(),* and *sweep_environments()*. These functions unmark objects if they are marked for the next
garbage collection. If objects are unmarked, they are deleted.
