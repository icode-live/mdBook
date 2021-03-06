# Rust Library

mdBook is not only a command line tool, it can be used as a crate. You can extend it,
integrate it in current projects. Here is a short example:

```rust,ignore
extern crate mdbook;

use mdbook::MDBook;
use std::path::Path;

fn main() {
    let mut book =  MDBook::new(Path::new("my-book"))   // Path to root
                        .set_src(Path::new("src"))      // Path from root to source directory
                        .set_dest(Path::new("book"))    // Path from root to output directory
                        .read_config();                 // Parse book.toml or book.json file for configuration

    book.build().unwrap();                              // Render the book
}
```

Check here for the [API docs](mdbook/index.html) generated by rustdoc.
