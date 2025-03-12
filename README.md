# PRISM

PRISM is a Rust-based system integrity and security framework designed to freeze OS changes using Vigil, unfreeze them with Eve, and audit modifications with PRISM Eye. It leverages AES-256 encryption and overlay filesystems to protect system integrity while providing a comprehensive audit trail.

# Usage / Features

| Syntax | Description |
| ----------- | ----------- |
| vigil | Freezes the OS disk, making changes appear writable but discarded upon reboot. Can be applied to a specific user `--user` or all users `--all`. Encrypts the frozen state with AES-256. |
| eve | Restores write access while maintaining audit logs of modifications. Decrypts the frozen state for continued operation. Can unfreeze for a specific user `--user` or all users `--all`. |
| eye | Displays a difference view of all file changes since the last freeze. `--blame` mode identifies which user modified each file. `--time` allows time-based change tracking. |
| refract | Restores files or full system state to a previous frozen snapshot. `--file` restores a specific file. `--all` restores the entire system. `--timestamp` allows restoration to a specific point in time. |
| spectra | Performs an integrity check comparing system state against the last freeze. `--deep` performs a byte-level comparison. `--quick` checks file metadata. `--export` saves the analysis report to a file. |
| aperture | Defines files or directories that remain writable while the system is frozen. `--add` specifies paths exempt from freezing. `--remove` deletes exemptions. `--list` displays all configured exceptions. |

-  AES-256 Encryption – Securely locks system state with a user-defined password.
-  Cross-Platform Support – Designed with modular expansion for multiple operating systems.
-  Audit Trail – Logs and tracks all changes made while the system is frozen.

# Installation
Prerequisites
```
Rust (latest stable version)
OverlayFS (for Linux) or an equivalent filesystem for other platforms
Root/admin privileges
```

# Building from Source

## Clone the repository
```
git clone https://github.com/yourusername/prism.git
cd prism
```
## Build the project
```
cargo build --release
```

# Contributing
Contributions are welcome! Please follow the contributing guidelines before submitting a PR.

# Disclaimer

Use PRISM at your own risk. Ensure you understand its functionality before freezing your system.

🚀 PRISM – Secure. Freeze. Audit.
