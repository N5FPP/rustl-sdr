# RusTL-SDR

A pure Rust implementation of the RTL-SDR driver, for shits and giggles.

This is mostly an exercise in writing low-level driver code.

Unusable, and highly unlikely to ever become usable. But it's fun.

For real alternatives check out the original [librtlsdr](https://github.com/osmocom/rtl-sdr/) implementation or the high-level [rtlsdr_mt](https://github.com/kchmck/rtlsdr_mt.rs) Rust bindings.

## Usage

Install the crate in your `Cargo.toml`:

```toml
[dependencies]
rustl-sdr = "0.1"
```

Use in your code:

```rust
extern crate libusb;
extern crate rustl_sdr;

fn foo() {
    let ctx = libusb::Context::new().unwrap();
    rtlsdr = rustl_sdr::RtlSdr::new(&ctx);
    rtlsdr.init();
    rtlsdr.do_stuff();
}
```

## Dev

The usual:

```bash
$ cargo build
$ cargo test -- --nocapture
```

Since there isn't (?) any good USB device mocking setup, for tests to pass an RTL-SDR device must be connected.

## License

[GPLv3](LICENSE)
