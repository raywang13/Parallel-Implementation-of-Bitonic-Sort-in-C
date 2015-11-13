# Parallel-Implementation-of-Bitonic-Sort-in-C

Bitonic sort is a sorting algorithm that proceeds by building sequences of keys that 
form a bitonic sequence: a sequence that first increases, then decreases. It then uses 
butterfly structures to sort a bitonic sequence into either a decreasing or increasing sequence.

Suppose first that I have a list of n integer keys, and n is a power of 2. Any pair of elements
can be turned into either an increasing or decreasing sequence by a merge-split operation.

I use a block partition, and assign n/p elements to each process (p = # of processes). Then
each process sorts its assigned sublist using a fast sorting algorithm using the C library
qsort function. After the sublists are sorted, we use a number of butterfly exchanges and merge-splits.
