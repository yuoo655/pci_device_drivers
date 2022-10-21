# run

```
cd example
cargo build --release
rust-objcopy --binary-architecture=riscv64 target/riscv64gc-unknown-none-elf/release/example -O binary os.bin
dd if=/dev/zero bs=1M count=16 of=nvme.img
make qemu-nvme
cat | head -c 1024 nvme.img | xxd
```