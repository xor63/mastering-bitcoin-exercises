# Mastering Bitcoin Exercises

This project provides supplementary exercises to the book Mastering Bitcoin 2nd
Edition by Andreas M. Antonopoulos.

## Building

Building the book requires [mdBook], specifically version 0.2.x. First,
[install Rust][rust]. Then install mdbook:

```bash
$ cargo install mdbook --vers 0.2
```

To build and then serve the book at `http://localhost:3000`, run:

```bash
$ mdbook serve
```

## License

"Mastering Bitcoin - Second Edition" by [Andreas M. Antonopoulos LLC][aantonop]
is licensed under [CC BY-SA 4.0][cc-by-sa].

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a>

"Mastering Bitcoin Exercises" is also licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[mdBook]: https://github.com/rust-lang-nursery/mdBook
[rust]: https://www.rust-lang.org/tools/install
[aantonop]: https://antonopoulos.com/
[cc-by-sa]: https://creativecommons.org/licenses/by-sa/4.0/
