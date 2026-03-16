[<img alt="Water programming language banner" width="100%" src="Banner.png" />](https://water.permille.io/)

# Water Programming Language

Water compiles easily maintainable high-level code directly to WebAssembly. It supports all of the newest WebAssembly features, covering [all stage 5 and 4 proposals](https://webassembly.org/features/), offering convenient abstractions for each feature together will full low-level access. Water supports template generics for classes and functions, arrow functions and closures, operator overloading, multivalued types, inline assembly, and many other modern language features such as all statements being expressions. Find out more [at the official website](https://water.permille.io/).

## Documentation

You can find comprehensive documentation for this programming language [here](https://water.permille.io/docs).

## Case study

This programming language has seen extensive use in the multiplatform [Permille.io voxel game engine](https://permille.io/), which runs entirely in a web browser. Water enabled the use of low-level performance enhancing intrinsics such as SIMD in a high-level fashion, drastically reducing development times while offering a 10x speed improvement over equivalent Javascript implementations (partly due to such performance enhancers not being accessible from Javascript). As Water is designed specifically for WebAssembly, easy integration with the ecosystem of the Web was possible, thus further demonstrating its practical utility. The end result is sub-second world loading times and near-native performance on the web.

## Contributing

This project is now open to contributions! Please feel free to push commits and open issues. You can also join the [community discord](https://discord.gg/bqBAjvvBGY).

## Project structure

This repository contains the compiler and infrastructure around the Water programming language. 
