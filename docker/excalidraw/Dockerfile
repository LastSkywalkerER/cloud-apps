FROM debian:bookworm-slim

# Install wget, ca-certificates, and sqlite3 libraries
RUN apt-get update && \
    apt-get install -y wget ca-certificates sqlite3 libsqlite3-0 && \
    rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /app

# Download and extract excalidraw-complete
RUN wget https://github.com/PatWie/excalidraw-complete/releases/download/0.0.2/excalidraw-complete_Linux_x86_64.tar.gz && \
    tar -xzf excalidraw-complete_Linux_x86_64.tar.gz && \
    rm excalidraw-complete_Linux_x86_64.tar.gz && \
    chmod +x excalidraw-complete

# Create data directory
RUN mkdir -p /app/data

# Expose port 3002
EXPOSE 3002

# Run the application
CMD ["./excalidraw-complete"]

