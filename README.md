# Top Down Embedded Rust

This is going to be a guide/book/workshop for Rust engineers to learn about embedded system programming with Rust.

## Abstract

In this book we will be building a basic [Snake](https://en.wikipedia.org/wiki/Snake_(video_game_genre)) game on the BBC micro:bit v2 using existing Rust tools and crates.

We will use the 5x5 LED matrix to display the game board. Use the buttons to control the snakes movement. Learn how to write the game logic without using Rusts standard library.

Having this proof of concept running we will dive into more specialized topics. These can be followed in any order as you see them interesting. We will communicate with the acceleration sensor on the board via I2C. Measure the noise level with the microphone. Add sound effects with the speaker. Persist the high-scores in non-volatile memory. We will explore how to add true randomness to our game using the on-chip timers and random number generator. And we will communicate to our PC using a serial interface.

I will cover electronics basics as side notes, but try to mostly link to good material that already covers things well.

## Why does this exist?

We do have quite a bit of public material about embedded Rust, like [The Embedded Rust Book](https://docs.rust-embedded.org/book/) or the [Rust Embedded MB2 Discovery Book](https://docs.rust-embedded.org/discovery-mb2/). However these books cover more of the low level aspects of embedded Rust whereas material that gets you started is more sparse.

I think there is space for an applied guide to getting started with embedded. Just like we have guides for web development that start out with building basic web apps instead of explaining the underlying protocols (e.g. HTTP, TLS, TCP) first.

## Structure

1. Getting running
    1. Discover the hardware
    2. Connect using probe-rs
    3. Print logs using defmt
2. Basic inputs and outputs
    1. Blinking an LED (Outputs)
    2. Keeping track of time (`embassy-time`)
    3. Reading Inputs
    4. Using Multiplexing for LED matrices
3. Writing `no_std` logic and apps
    1. Common architectures
    2. Heapless
    3. Testing
4. Expanding the game
    1. Using tilt as game input (Accelerometer, I2C)
    2. Measuring noise (Microphone, ADC)
    3. Producing noise (Speaker, PWM)
    4. Keeping high-scores (sequential-storage)
    5. Adding randomness (Timers, TRNG)
    6. Talking to other machines (UART)
