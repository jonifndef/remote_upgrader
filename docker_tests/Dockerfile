# Use the official Ubuntu base image
FROM ubuntu:latest

# Prevent interactive prompts during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Update package list and install SSH server
RUN apt-get update && apt-get install -y openssh-server sudo

# Create the SSH directory
RUN mkdir /var/run/sshd

# Create a new user called 'user' with password 'password'
RUN useradd -m user && echo "user:password" | chpasswd && usermod -aG sudo user

# Allow password authentication for SSH
RUN sed -i 's/#PasswordAuthentication yes/PasswordAuthentication yes/' /etc/ssh/sshd_config

# Expose the SSH port
EXPOSE 22

# Start the SSH server
CMD ["/usr/sbin/sshd", "-D"]
