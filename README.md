# Arc
Novusk-based OS running the Ardaku engine.

## Build Environment
You will need the nightly toolchain and sources as well as cargo-binutils.

```commandline
rustup toolchain install nightly
rustup component add rust-src --toolchain nightly-x86_64-unknown-linux-gnu
rustup component add llvm-tools-preview
cargo install cargo-binutils
```

## Build:

Use ``aarch64`` for arm (64 bit), and riscv (32 bit for now)

```commandline
make all ARCH=<architecture>
```

## Test ARM in QEMU
The OS executable will be located at ``./target/aarch64-novusk/release/kernel8.img``
Make sure you have at least Qemu v4.2.1+

```commandline
qemu-system-aarch64 -M raspi3 -kernel target/aarch64-novusk/release/kernel8.img
```

## Test RISC-V in QEMU
TODO

## Test on Raspberry Pi

[TODO](link_to_novusk_docs)

Install the Raspberry Pi boot files from [here](https://github.com/raspberrypi/firmware/tree/master/boot) and replace 
``kernel8.img`` with ``target/aarch64-novusk/release/kernel8.img``
