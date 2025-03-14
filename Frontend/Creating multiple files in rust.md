Tag: [[WASM]]


## Using Multiple Files with Rust and wasm-pack

To organize your Rust code into multiple files, you can use Rust's module system. Here's how you can structure your project:

1. **Create a `lib.rs` file**: This will serve as the entry point for your library.
    
2. **Define modules**: Create separate files for each module you want to define. For example, you might have `utils.rs`, `math.rs`, etc.
    
3. **Use `mod` keyword**: In your `lib.rs`, use the `mod` keyword to declare these modules.
    

## Example Structure

text

`src/ |- lib.rs |- utils.rs |- math.rs Cargo.toml`

## lib.rs Example

rust

`// lib.rs
mod utils;
mod math;
#[wasm_bindgen]
pub fn greet(name: &str) {     
utils::print_greeting(name); }
#[wasm_bindgen] 
pub fn add(a: i32, b: i32) -> i32 
{     math::add(a, b) }`

## utils.rs Example

rust

`// utils.rs pub fn print_greeting(name: &str) {     println!("Hello, {}!", name); }`

## math.rs Example

rust

`// math.rs pub fn add(a: i32, b: i32) -> i32 {     a + b }`

## Understanding `#[wasm_bindgen]`

The `#[wasm_bindgen]` attribute is used by the `wasm-bindgen` tool to facilitate interactions between Rust and JavaScript. It allows you to:

- **Export Rust functions to JavaScript**: By placing `#[wasm_bindgen]` above a Rust function, you can call that function from JavaScript.
    
- **Import JavaScript functions into Rust**: You can also use `#[wasm_bindgen]` to import JavaScript functions into your Rust code, allowing Rust to call JavaScript functions.
    

Here's an example of exporting a Rust function to JavaScript:

rust

`#[wasm_bindgen] pub fn greet(name: &str) {     println!("Hello, {}!", name); }`

And here's how you might import and use a JavaScript function in Rust:

rust

`#[wasm_bindgen] extern "C" {     #[wasm_bindgen(js_namespace = console)]    fn log(s: &str); } pub fn greet(name: &str) {     log(&format!("Hello, {}!", name)); }`

This setup allows for seamless communication between Rust and JavaScript when using WebAssembly.



---

Answer from Perplexity: pplx.ai/share