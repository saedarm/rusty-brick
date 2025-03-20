# Rust Yew Breakout Game

A classic Breakout game implementation using Rust and the Yew framework to create a WebAssembly-powered browser game.

![Breakout Game Screenshot](https://fity.club/lists/suggestions/atari-breakout-game-online)
## Features

- Paddle controlled with arrow keys
- Physics-based ball movement
- Colorful brick patterns
- Score tracking
- Lives system
- Game state management (Start, Playing, Game Over)
- Responsive paddle movement

## Prerequisites

Before you begin, ensure you have the following installed:

- [Rust](https://www.rust-lang.org/tools/install) (latest stable version)
- [Cargo](https://doc.rust-lang.org/cargo/getting-started/installation.html) (comes with Rust)
- [wasm-pack](https://rustwasm.github.io/wasm-pack/installer/)
- [Trunk](https://trunkrs.dev/) - The WASM web application bundler for Rust

## Setup Instructions

### 1. Install Rust and Cargo

If you don't have Rust installed, visit [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install) and follow the instructions for your operating system.

Verify your installation:

```bash
rustc --version
cargo --version
```

### 2. Install WebAssembly Target

Add the WebAssembly target to your Rust toolchain:

```bash
rustup target add wasm32-unknown-unknown
```

### 3. Install Trunk

Trunk is a build tool for WebAssembly applications written in Rust:

```bash
cargo install trunk
```

### 4. Create New Project

Create a new Rust project:

```bash
cargo new yew-breakout
cd yew-breakout
```

### 5. Project Structure

Set up the following project structure:

```
yew-breakout/
├── Cargo.toml
├── index.html
└── src/
    ├── main.rs
    └── components/
        ├── mod.rs
        ├── game.rs
        ├── paddle.rs
        ├── ball.rs
        └── brick.rs
```

Create the required directories:

```bash
mkdir -p src/components
```

### 6. Configure Dependencies

Replace the contents of `Cargo.toml` with:

```toml
[package]
name = "yew-breakout"
version = "0.1.0"
edition = "2021"

[dependencies]
yew = "0.20"
wasm-bindgen = "0.2"
web-sys = { version = "0.3", features = [
    "Window",
    "Document",
    "Element",
    "HtmlElement",
    "DomRect",
    "Performance",
    "KeyboardEvent",
    "AddEventListenerOptions",
    "AnimationFrameProvider",
    "console",
]}
gloo-timers = "0.2"
gloo-events = "0.1"
js-sys = "0.3"
rand = "0.8"
getrandom = { version = "0.2", features = ["js"] }
```

### 7. Create HTML Template

Create an `index.html` file in the project root with:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>Rust Yew Breakout</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background-color: #333;
            font-family: Arial, sans-serif;
        }
        
        .app-container {
            text-align: center;
        }
        
        h1 {
            color: white;
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div id="app"></div>
</body>
</html>
```

### 8. Implement Components

Create the following files with their respective contents:

#### `src/main.rs`
Copy the content from the `src/main.rs` section in the code artifact.

#### `src/components/mod.rs`
Copy the content from the `src/components/mod.rs` section in the code artifact.

#### `src/components/game.rs`
Copy the content from the `src/components/game.rs` section in the code artifact.

#### `src/components/paddle.rs`
Copy the content from the `src/components/paddle.rs` section in the code artifact.

#### `src/components/ball.rs`
Copy the content from the `src/components/ball.rs` section in the code artifact.

#### `src/components/brick.rs`
Copy the content from the `src/components/brick.rs` section in the code artifact.

### 9. Building and Running

To build and serve the project locally:

```bash
trunk serve
```

This will:
1. Compile your Rust code to WebAssembly
2. Bundle your assets
3. Start a local development server

Open your browser and navigate to `http://localhost:8080` to play the game.

## How to Play

1. Press **SPACE** to start the game
2. Use **LEFT** and **RIGHT** arrow keys to move the paddle
3. Prevent the ball from falling below the paddle
4. Break all the bricks to win
5. You have 3 lives - game over when all lives are lost

## Customizing the Game

You can customize various aspects of the game by modifying constants in `src/components/game.rs`:

- `CANVAS_WIDTH` and `CANVAS_HEIGHT`: Change the game dimensions
- `PADDLE_WIDTH` and `PADDLE_HEIGHT`: Adjust paddle size
- `BALL_RADIUS`: Change the ball size
- `BRICK_ROWS` and `BRICK_COLUMNS`: Modify the brick layout
- Brick colors can be changed in the color array within the brick creation code

## Building for Production

To build optimized assets for production:

```bash
trunk build --release
```

The compiled files will be available in the `dist` directory.

## Troubleshooting

### Common Issues

1. **Compilation Errors**
   - Ensure all dependencies are correctly specified in `Cargo.toml`
   - Verify you have the correct Rust target installed

2. **Runtime Errors**
   - Check the browser console for JavaScript errors
   - Ensure your browser supports WebAssembly

3. **Performance Issues**
   - Try building with the `--release` flag for optimized performance

## Resources

- [Rust Documentation](https://www.rust-lang.org/learn)
- [Yew Framework](https://yew.rs/)
- [Trunk Documentation](https://trunkrs.dev/)
- [WebAssembly](https://webassembly.org/)

## License

MIT License

## Acknowledgements

- The classic Breakout game originally by Atari
- The Rust and Yew communities for their excellent tools and documentation
