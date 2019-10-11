This repository covers the following recipe from code.activestate.com:

[COMPUTE MEMORY FOOTPRINT OF AN OBJECT AND ITS CONTENTS](https://code.activestate.com/recipes/577504/)

*Created by Raymond Hettinger on Fri, 17 Dec 2010*

Recursive version sys.getsizeof(). Extendable with custom handlers.

By itself, the builtin function sys.getsizeof() is not helpful determining the size of a container and all of its contents.

This recipe makes it easy to find the memory footprint of a container and its context. Builtin containers and their subclasses are all fully supported. Extensions are provided for user-defined containers.

## Usage

If you already have the [State Tool] installed you can simply run

```
state activate ActiveState-Recipes/recipe-577504-compute-mem-footprint
```

If you do not have the [State Tool] installed you can use the following convenient one-liner.

Linux: 
```
sh <(curl -q https://platform.activestate.com/dl/cli/install.sh) && state activate ActiveState-Recipes/recipe-577504-compute-mem-footprint
```

Windows: 
```
powershell "IEX(New-Object Net.WebClient).downloadString('https://platform.activestate.com/dl/cli/install.ps1')" && state activate ActiveState-Recipes/recipe-577504-compute-mem-footprint
```

macOS: not yet supported

[State Tool]: https://www.activestate.com/products/platform/state-tool/
