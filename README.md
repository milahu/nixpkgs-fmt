# nixpkgs-fmt

**STATUS: alpha**

This project's goal is to provide a nix code formatter that would be applied
on nixpkgs. Ideally automatically with a tool like ofborg.

## Design decisions

Use Rust because ofborg is written in rust. Rust also has a small chance of
being included in nix upstream.

Use a rule-based formatter (vs pretty-printing) because it allows some form of
expressivity for the developers. For example double new-lines can be used when
the developer wants a section of code to stand out. The important part is to
avoid discussions on indent and brackets alignment.

Favour mergeability. nixpkgs is seeing a lot of traffic. Spread things out
vertically to minimize the chances of merge conflicts.

## Documents

* [HOWTO write new rules](docs/howto_rules.md)
* [HOWTO WASM](wasm/README.md)

## Related projects

* [hnix](https://github.com/haskell-nix/hnix) - Haskell implementation of Nix
  including a parser. The parser is not comment-preserving.
* [rnix](https://gitlab.com/jD91mZM2/rnix) - Rust Nix parser based on
  [rowan](https://github.com/rust-analyzer/rowan)
* [nix-lsp](https://gitlab.com/jD91mZM2/nix-lsp) - Nix language server using
  rnix
* [tree-sitter-nix](https://github.com/cstrahan/tree-sitter-nix) - Tree Sitter
  is a forgiving parser used by Atom for on-the-fly syntax highlighting and
  others. This is a implementation for Nix.
* [format-nix](https://github.com/justinwoo/format-nix/) - A nix formatter
  using tree-sitter-nix.
* [nixfmt](https://github.com/serokell/nixfmt) - A nix formatter written in
  Haskell.
* [nix-fmt](https://github.com/jmackie/nix-fmt)
* [nix-format](https://github.com/taktoa/nix-format) - Emacs-based Nix formatter
* [nix-beautify](https://github.com/nixcloud/nix-beautify)
* [nix-linter](https://github.com/Synthetica9/nix-linter)
* [canonix](https://github.com/hercules-ci/canonix/) - Nix formatter prototype written in Haskell using tree-sitter-nix grammar.

## Discussions

* [nixpkgs style guide](https://nixos.org/nixpkgs/manual/#sec-syntax)
* [On Nix expression formatting](https://discourse.nixos.org/t/on-nix-expression-formatting/1521/14)
* [[Job] Implement a `nix-fmt` formatter](https://discourse.nixos.org/t/job-implement-a-nix-fmt-formatter/2819/12)
