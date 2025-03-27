# compile-dotenv

Add environment variables defined in the environment or in a `.env` file at compile time.

## Description

The `compile-dotenv` library helps you manage environment variables by allowing you to inject them at compile time.

This can be particularly useful for configuring applications across different environments without hardcoding sensitive or environment-specific data.

## Features

- Load environment variables from a `.env` file.
- Inject environment variables during the compilation process.
- Simplify environment configuration for your Rust applications.

## Installation

To add `compile-dotenv` to your project, add the following line to your `Cargo.toml` file:

```toml
[dependencies]
compile-dotenv = "0.1.0"
```

## Usage

Here is a simple example of how to use `compile-dotenv` in your Rust project:

1. Create a `.env` file in the root of your project:
    ```
    SENTRY_DSN=https://examplePublicKey@o0.ingest.sentry.io/0
    ```

2. Use `compile-dotenv` to instantiate a Sentry guard in your `main.rs` or any other part of your application:
    ```rust
    use compile_dotenv::compile_env;

    fn main() {
        let _guard = sentry::init(compile_env!("SENTRY_DSN"));

        // ...
    }
    ```
