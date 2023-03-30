# graph-markup-lang
A markup language for graphs.

> The name is temporay

## The Pitch

Nearly all existing markup languages can only represent tree-like or list-like data structures. Whenever we need to serialize graph-like data, or data that contains references to other data, we need to come up with some unofficial extension to these markup languages. This is not a portable solution, so it defeats the purpose of serialization in the first place: being able to communicate data agnostically.

GML proposes a solution to this problem, while resembling popular markup languages like JSON or YAML enough to be easily understandable. The specification is deliberately minimal, so as to allow easy adoption and adherence to the standard (unlike YAML, which is very bloated). It also is devoid of weird quirks that make other markup languages counterintuitive, such as JSON's weird handling of type conversions, inherited from JavaScript.

GML is robust, simple and intuitive, and constitutes a great foundation to construct abstract serialization schemes, protocols and file formats on top of it.

You can easily represent traditional hierarchical data in GML:

```
user_info {
  name: Kirby,
  age: 27,
  gender: "non binary",
}
```

But you can enrich it with relational data:

```
people {
  Martha,
  Carissa,
  Harold,
  Roger,
  Sam,
  
  Martha -> Carissa -> Harold: sibling,
  Harold -> Roger: partner,
  Sam -> Harold: cousin,
}
```

## Further Reading

- [Introduction]()
- [Official Reference]()
- [Examples]()

## References

Official implementations:
- Python: [PyPI]() TODO
- Rust: [Crates.io]() TODO
- C: [GitHub]() TODO
- VSCode Language Support: [VSCode]()
