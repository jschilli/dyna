# Dyna

Dyna is a component interface and host support library that allows a component at runtime to instantiate another component and then perform reflection on that component's exports and call exported functions. 

## Show me more

Here is some example Rust code using the `dyna` package's `dynamic-component` interface:

```rust
// Read a component from disk
let component_bytes = std::fs::read("some_component.wasm").unwrap();
// Create a component engine and load the component
let engine = Engine::new();
let component = engine.load_component(&component_bytes).unwrap();
// Reflect on the component to gain insight into its exports
println!("{:#?}", component.reflect());
// Call a component export
let val = component.call("hello-world", &[]);
```
