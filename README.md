# Image Processing Library in C++

# Overview

This library provides a templated `Image` class for working with 2D images of various data types. It supports basic image operations including arithmetic operations, concatenation, cropping, and more.

# Key Features

- Templated `Image<T>` class supporting different pixel data types
- Arithmetic operations between images (+, -, *, /)
- Scalar operations
- Horizontal and vertical image concatenation
- Image cropping (both template-based and dynamic methods)
- Error handling and exceptions
- Interactive menu for demonstrating functionality

# Getting Started

# Basic Usage

1. Include the header file in your project
2. Create `Image` objects with your desired data type
3. Perform operations using the provided methods

# Example

#include "Image.hpp"

int main() {
    // Create two 3x3 images
    Image<int> img1(3, 3, 1);  // 3x3 filled with 1s
    Image<int> img2(3, 3, 2);  // 3x3 filled with 2s
    
    // Perform operations
    auto sum = img1 + img2;      // Element-wise addition
    auto scaled = img1 * 5;      // Scalar multiplication
    auto cropped = img1.subimageDynamic(0, 1, 0, 1);  // 2x2 top-left crop
    
    return 0;
}

# Class Methods Reference

# Constructors

| Method | Description |
|--------|-------------|
| `Image()` | Creates empty image |
| `Image(height, width, defaultValue)` | Creates image with specified dimensions |
| `Image(otherImage)` | Copy constructor |
| `Image<U>(otherImage)` | Conversion constructor |

# I/O Operations

| Method | Description |
|--------|-------------|
| `input()` | Reads image data from console |
| `print()` | Outputs image to console |

# Pixel Access

| Method | Description |
|--------|-------------|
| `setPixel(row, col, value)` | Sets pixel value |
| `getPixel(row, col)` | Gets pixel value |
| `pixel(row, col)` | Access with negative index support |

# Image Operations

| Method | Description |
|--------|-------------|
| `operator+(image)` | Element-wise addition |
| `operator-(image)` | Element-wise subtraction |
| `operator*(image)` | Element-wise multiplication |
| `operator/(image)` | Element-wise division |
| `concatHorizontal(image)` | Horizontal concatenation |
| `concatVertical(image)` | Vertical concatenation |
| `subimageDynamic()` | Runtime cropping |
| `subimage<>()` | Compile-time cropping |

# Scalar Operations

| Method | Description |
|--------|-------------|
| `operator+(scalar)` | Add scalar to each pixel |
| `operator-(scalar)` | Subtract scalar from each pixel |
| `operator*(scalar)` | Multiply each pixel by scalar |
| `operator/(scalar)` | Divide each pixel by scalar |

# Interactive Menu System

The included `main()` function provides an interactive menu with these options:

1. Create a new image
2. Display the image
3. Horizontally merge images
4. Vertically merge images
5. Add images
6. Multiply the image by a scalar
7. Crop the image
8. Subtract one image from another
9. Divide one image by another
10. Subtract a scalar from the image
11. Divide the image by a scalar
0. Exit

# Requirements

- C++11 or newer
- Standard libraries: `<iostream>`, `<vector>`, `<iomanip>`, `<type_traits>`, `<limits>`, `<stdexcept>`

# Error Handling

The library throws exceptions for:
- Dimension mismatches in operations
- Division by zero
- Out-of-bounds access (when not using negative indices)

# Best Practices

1. Always check image dimensions before operations
2. Handle exceptions for division operations
3. Use `subimageDynamic()` for runtime cropping and `subimage<>()` for compile-time cropping
4. Consider memory usage for large images

# Limitations

- Currently supports only console I/O
- No image file format support
- Basic error handling implementation

# Contribution

Contributions are welcome. Please ensure:
- Backward compatibility is maintained
- New features include proper error handling
- Code follows the existing style
