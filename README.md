ks
==

**ks** is a minimal library that implements lazy
datastructures, i.e. **Stream**s, **Queue**s, etc.
with a focus on elegance and performance. The library
can be used to provide lazily evaluated data for
computationally intensive operations, or for huge
datasets that do not fit in memory.

Examples of using the provided **Mapping** class, a
lazy, read-only dictionary-like interface:

```python
def iterator():
    for item in range(100):
        yield item + 1, item

d = Mapping(iterator())
assert d[100] == 99
assert len(d) == 100
```

Note that since the datastructures are lazy, most
classes that provide ``len`` magic will not be able
to deterministically return their sizes.
