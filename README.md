# Malloc & Free Implementation

# Table of Contents
- [Malloc \& Free Implementation](#malloc--free-implementation)
- [Table of Contents](#table-of-contents)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Building the Library](#building-the-library)
- [Usage](#usage)
- [Features](#features)
- [Contributing](#contributing)
- [Copyright](#copyright)

# Getting Started
## Prerequisites
Ensure that you have the `make` file 

## Building the Library
To build the library, navigate to the top-level directory and type:
```
make
```
# Usage
Once you have the library, you can use it to override the existing `malloc` by using `LD_PRELOAD`.

For example, to run the `ffnf` test using the First Fit shared library:
```
$ env LD_PRELOAD=lib/libmalloc-ff.so tests/ffnf
```
To run the other heap management schemes, replace `libmalloc-ff.so` with the appropriate library:

- Best-Fit: `libmalloc-bf.so`
- First-Fit: `libmalloc-ff.so`
- Next-Fit: `libmalloc-nf.so`
- Worst-Fit: `libmalloc-wf.so`

# Features
This library implements the following features:


1. **Splitting and coalescing of free blocks:** If two free blocks are adjacent, then the library combines them. If a free block is larger than the requested size, then the library splits the block into two.
2. **Different heap management strategies:** The library supports four different heap management strategies - Next Fit, Worst Fit, Best Fit, and First Fit.
3. **Detailed tracking:** The library keeps track of several events:
    - Number of times malloc is called successfully
    - Number of times free is called successfully
    - Number of times an existing block is reused
    - Number of times a new block is requested
    - Number of times a block is split
    - Number of times blocks are coalesced
    - Number of blocks in the free list
    - Total amount of memory requested
    - Maximum size of the heap

# Contributing
Feel free to open issues or pull requests, I'd love to have your feedback or collaborate with you!

# Copyright

Copyright © 2023. All rights reserved.

This software is provided for educational purposes only. It is prohibited to use this Malloc Implementation, for any college assignment or personal use. Unauthorized distribution, modification or commercial usage is strictly forbidden. Please respect the rights of the author.



