//cargo build --release --target=x86_64-pc-windows-gnu

FROM rust:latest

RUN apt update && apt upgrade -y
RUN apt install -y g++-mingw-w64-x86-64 gcc-mingw-w64-x86-64

RUN rustup target add x86_64-pc-windows-gnu
RUN rustup toolchain install stable-x86_64-pc-windows-gnu

# Add the following lines to ~/.cargo/config:
#   [target.x86_64-pc-windows-gnu]
#   linker = "x86_64-w64-mingw32-gcc"
#   ar = "x86_64-w64-mingw32-gcc-ar"

ADD . / app/
WORKDIR /app

CMD ["cargo", "build", "--target", "x86_64-pc-windows-gnu"]