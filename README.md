# **Humansize**
Humansize lets you easily represent file sizes in a human-friendly format.
You can specify your own formatting style, pick among the three defaults provided
by the library:

* Decimal (Multiples of 1000, `KB` units)
* Binary (Multiples of 1024, `KiB` units)
* Conventional (Multiples of 1024, `KB` units)

## How to use it
Simply import the `FileSize` trait and the options module and call the
file_size method on any positive integer, using one of the three standards
provided by the options module.

```rust
extern crate humansize;
use humansize::{FileSize, file_size_opts as options};

fn main() {
	let size = 1000;
	println!("Size is {}", size.file_size(options::DECIMAL).unwrap());

	println!("Size is {}", size.file_size(options::BINARY).unwrap());

	println!("Size is {}", size.file_size(options::CONVENTIONAL).unwrap());
}
```

If you wish to customize the way sizes are displayed, you may create your own custom `FileSizeOpts` struct
and pass that to the method. See the `custom_options.rs` file in the example folder.
