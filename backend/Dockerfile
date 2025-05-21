# 🛠️ Stage 1: Build the backend
FROM rust:1.71 as builder                    
WORKDIR /app
COPY backend/ ./                             

# 🧰 Install system dependencies for certain crates (like OpenSSL)
RUN apt-get update && apt-get install -y pkg-config libssl-dev

# 🏗️ Build the Rust app in release mode
RUN cargo build --release 

# 🚀 Stage 2: Runtime container
FROM debian:bullseye-slim                    

# 🗂️ Copy the built binary from the builder stage
COPY --from=builder /app/target/release/backend /usr/local/bin/backend

# 🌐 Expose the port your app uses
EXPOSE 8080

# ▶️ Start the application when the container runs
CMD ["bencher"]
# You can replace this with a custom run if needed:
# CMD ["bencher", "--host", "0.0.0.0"]
