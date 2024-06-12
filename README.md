# MeshGrid.jl

[![Build Status](https://github.com/akjake616/MeshGrid.jl/actions/workflows/CI.yml/badge.svg)](https://github.com/akjake616/MeshGrid.jl/actions/workflows/CI.yml)

## Overview

`MeshGrid.jl` is a simple Julia module that provides functionality similar to MATLAB's `meshgrid` function. It generates coordinate matrices from vectors or ranges, which are useful for evaluating functions over a grid in two or three dimensions.

## Installation

To install `MeshGrid.jl`, use the following command in the Julia REPL:

```julia
using Pkg
Pkg.add("MeshGrid")
```

## Some Examples

These examples illustrate how `MeshGrid.jl` can handle different data types and mixed types. This flexibility makes it easier to translate MATLAB code into Julia, providing a familiar interface for those transitioning from MATLAB to Julia. Note that the element data type of the output grid will be the promotion of the input element data types.

### Example 1: Creating 2D Grid from Range

```julia
x = -1:1:1
y = -1:0.5:1

X, Y = meshgrid(x, y)
```

### Example 2: Mixing Integers and Floats in 2D Grid

```julia
x = 1:3  # integer range
y = [1.0, 2.5, 4.0]  # Float vector

X, Y = meshgrid(x, y) # elements are promoted to Float64
```

### Example 3: Fusing Different Data Types to form 3D Grid

```julia
x = 1:3  # integer range
y = [1.0, 2.5, 4.0]  # float vector
z = ["alice", "bob"] # string vector

X, Y, Z = meshgrid(x, y, z) # elements are promoted to Any
```

