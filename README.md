# Secure Homelab Minecraft Stack

Traditional port forwarding often exposes infrastructure to unnecessary risks, particularly when self-hosting game servers. To address this, I have implemented a **Zero-Trust networking approach** using **Tailscale**.

This setup ensures the server is accessible only via an encrypted, authenticated mesh VPN, effectively eliminating the need for public-facing ports.

## Technical Stack
* **Orchestration:** Docker & Docker Compose
* **Management:** Crafty Controller
* **Networking:** Tailscale (WireGuard-based mesh VPN)

## Security Posture
* **Infrastructure Hardening:** Public port exposure is disabled. All traffic is routed through an authenticated Tailscale overlay network.
* **Secret Management:** Sensitive data, including environment variables, SSL certificates, and Tailscale authentication keys, are excluded from version control using `.gitignore` to prevent exposure.
* **Database Isolation:** Database files and persistent state caches are kept local and excluded from the public repository.
