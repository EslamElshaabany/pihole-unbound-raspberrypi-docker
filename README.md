# Pi-hole with Unbound on Raspberry Pi (Docker)

This project sets up Pi-hole with Unbound using Docker on a Raspberry Pi, providing an ad-blocking and recursive DNS solution.

## Prerequisites

- Raspberry Pi with Docker installed
- Internet connection for cloning the repository and downloading dependencies

## Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/EslamElshaabany/pihole-unbound-raspberrypi-docker.git
   ```

2. **Download Root Hints**:
   Fetch the latest DNS root hints file for Unbound:
   ```bash
   wget https://www.internic.net/domain/named.root -qO- > root.hints
   ```

3. **Run the Containers**:
   Start the Pi-hole and Unbound containers using Docker Compose:
   ```bash
   docker compose up -d
   ```

## Network Configuration

Ensure your Raspberry Pi allows traffic from your local network on the following ports:

- `22/tcp` (SSH)
- `53/tcp` (DNS)
- `53/udp` (DNS)
- `80/tcp` (HTTP)
- `443/tcp` (HTTPS)

## Notes

- Verify that Docker and Docker Compose are properly installed before starting.
- Ensure the `root.hints` file is in the correct directory as specified in your Unbound configuration.
- For troubleshooting or customization, refer to the [Pi-hole documentation](https://docs.pi-hole.net/) and [Unbound documentation](https://nlnetlabs.nl/documentation/unbound/).
