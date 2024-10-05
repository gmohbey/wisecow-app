# Use Debian 12.5 as the base image
FROM debian:12.7

# Set environment variable for the server port
ENV SRVPORT=4499

# Update package list and install required packages
RUN apt-get update && \
    apt-get install -y cowsay fortune-mod netcat-openbsd && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /app

# Copy the shell script into the container
COPY wisecow.sh /app/wisecow.sh

# Make the shell script executable
RUN chmod +x /app/wisecow.sh

# Ensure the PATH includes /usr/games so that cowsay and fortune can be found
ENV PATH="/usr/games:${PATH}"

# Expose the necessary port
EXPOSE 4499

# Set the entrypoint to run the shell script
ENTRYPOINT ["/app/wisecow.sh"]
