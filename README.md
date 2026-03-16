[<img alt="Water programming language banner" width="100%" src="Banner.png" />](https://water.permille.io/)

# Water Programming Language

Water compiles easily maintainable high-level code directly to WebAssembly. It supports all of the newest WebAssembly features, covering [all stage 5 and 4 proposals](https://webassembly.org/features/), offering convenient abstractions for each feature together will full low-level access. Water supports template generics for classes and functions, arrow functions and closures, operator overloading, multivalued types, inline assembly, and many other modern language features such as all statements being expressions. Find out more [at the official website](https://water.permille.io/).

## Documentation

You can find comprehensive documentation for this programming language [here](https://water.permille.io/docs).

## Installation

Use `npm install water-lang` to install this package.

This package contains the compiler, which converts valid Water source code to a WebAssembly binary. It can be used directly like this:

```js
import Compile from "water-lang/Compile";

const CompiledBinary = Compile(`
  export "Add" i32 Add(i32 a, i32 b) a + b;
`);

const Module = new WebAssembly.Module(CompiledBinary);
const Instance = new WebAssembly.Instance(Module);

console.log(Instance.exports.Add(11, 22)); // 33
```

### Webpack

If you are using Webpack, a loader is included in this package for your convenience.

To use the loader, you will need to modify the Webpack configuration file in your project, typically named `webpack.common.js`, and add the following new configuration entry under the `module.exports.module.rules` array:

```js
{
  "test": /\.(water|wtr)$/i,
  "use": ["water-lang/Webpack"]
}
```

To clarify, the configuration should look something like this in the end:

```js
module.exports = {
  "module": {
    "rules": [
      {
        "test": /\.(water|wtr)$/i,
        "use": ["water-lang/Webpack"]
      },
      // ...
    ],
    // ...
  },
  // All other configuration entries ...
};
```

After this is done, you will be able to import compiled versions of Water files directly into your Javascript files:

```js
import CompiledBinary from "./Add.water"; // The `.wtr` extension also works

const Module = new WebAssembly.Module(CompiledBinary);
const Instance = new WebAssembly.Instance(Module);

console.log(Instance.exports.Add(11, 22));
```

### Other loaders

Support for other loaders has not been implemented yet, but if you would like to contribute, please open an issue or pull request on Github.

## Case study

This programming language has seen extensive use in the multiplatform [Permille.io voxel game engine](https://permille.io/), which runs entirely in a web browser. Water enabled the use of low-level performance enhancing intrinsics such as SIMD in a high-level fashion, drastically reducing development times while offering a 10x speed improvement over equivalent Javascript implementations (partly due to such performance enhancers not being accessible from Javascript). As Water is designed specifically for WebAssembly, easy integration with the ecosystem of the Web was possible, thus further demonstrating its practical utility. The end result is sub-second world loading times and near-native performance on the web.

## Credits

This project depends on [Binaryen](https://github.com/WebAssembly/binaryen) and [its port to Javascript](https://github.com/AssemblyScript/binaryen.js/) by the AssemblyScript team.

This project would not have been possible without the excellent work of all of Binaryen's contributors!
The same goes for the WebAssembly standardisation team. Thank you all :)

All other code and supporting documentation has been written exclusively by me up to this point, *without the use of AI technology*, to ensure a high standard of quality and reliability.

## Contributing

This project is now open to contributions! Please feel free to push commits and open issues. You can also join the [community discord](https://discord.gg/bqBAjvvBGY).

## Project structure

This repository contains the compiler and infrastructure around the Water programming language. 
