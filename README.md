<h1 align="center">jaxtyping</h1>

Type annotations **and runtime checking** for:

1. shape and dtype of [JAX](https://github.com/google/jax) arrays;
2. [PyTrees](https://jax.readthedocs.io/en/latest/pytrees.html).

**For example:**
```python
from jaxtyping import Array, Float, PyTree

# Accepts floating-point 2D arrays with matching dimensions
def matrix_multiply(x: Float[Array, "dim1 dim2"],
                    y: Float[Array, "dim2 dim3"]
                  ) -> Float[Array, "dim1 dim3"]:
    ...

def accepts_pytree_of_ints(x: PyTree[int]):
    ...

def accepts_pytree_of_arrays(x: PyTree[Float[Array, "batch c1 c2"]]):
    ...
```

## Installation

```bash
pip install jaxtyping
```

Requires JAX 0.3.4+.

Also install your favourite runtime type-checking package. The two most popular are [typeguard](https://github.com/agronholm/typeguard) (which exhaustively checks every argument) and [beartype](https://github.com/beartype/beartype) (which checks random pieces of arguments).

## Documentation

[Full API reference](./API.md)

[FAQ (static type checking, flake8, etc.)](./FAQ.md)

## Finally

### See also: other tools in the JAX ecosystem

Neural networks: [Equinox](https://github.com/patrick-kidger/equinox).

Numerical differential equation solvers: [Diffrax](https://github.com/patrick-kidger/diffrax).

Computer vision models: [Eqxvision](https://github.com/paganpasta/eqxvision).

SymPy<->JAX conversion; train symbolic expressions via gradient descent: [sympy2jax](https://github.com/google/sympy2jax).

### Acknowledgements

Shape annotations + runtime type checking is inspired by [TorchTyping](https://github.com/patrick-kidger/torchtyping).

The concise syntax is partially inspired by [etils.array_types](https://github.com/google/etils/tree/main/etils/array_types).

### Disclaimer

This is not an official Google product.
