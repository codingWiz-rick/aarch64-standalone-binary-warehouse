# 🚀 AArch64 Standalone Binary Warehouse

<div align="center">

![ARM64](https://img.shields.io/badge/Architecture-ARM64-orange?style=for-the-badge&logo=arm&logoColor=white)
![Musl](https://img.shields.io/badge/Toolchain-Musl-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Linux-green?style=for-the-badge&logo=linux&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)
![Maintained](https://img.shields.io/badge/Maintained-Yes-success?style=for-the-badge)
![Binaries](https://img.shields.io/badge/Binaries-50+-purple?style=for-the-badge)

**A comprehensive collection of standalone, statically-linked binaries built with musl libc for ARM64/AArch64 Linux systems**

[Browse Binaries](#-available-binaries) • [Quick Start](#-quick-start) • [Installation](#-installation) • [Contributing](#-contributing)

</div>

---

## 📖 Overview

This repository provides a curated collection of essential command-line tools and utilities compiled as standalone, statically-linked binaries for **AArch64 (ARM64)** architecture. All binaries are built using the **musl libc** toolchain, ensuring maximum portability and minimal runtime dependencies. Perfect for embedded systems, containers, minimal installations, and environments where package managers are unavailable.

### ✨ Key Features

- 🔧 **Zero Dependencies** - All binaries are statically linked with musl libc
- 📦 **Standalone Operation** - No installation required, just download and run
- 🏗️ **ARM64 Native** - Optimized for AArch64 architecture
- 🎯 **Musl-based** - Built with musl toolchain for maximum portability
- 🪶 **Lightweight** - Smaller binaries compared to glibc builds
- 🔒 **Security Focused** - Regular updates and security patches
- ⚡ **Performance Optimized** - Compiled with architecture-specific optimizations
- 🐧 **Universal Compatibility** - Works on any ARM64 Linux distribution (glibc or musl)

## 🎯 Use Cases

- **Embedded Systems** - Deploy tools on resource-constrained devices
- **Docker Containers** - Minimize container size with standalone binaries
- **Recovery Systems** - Essential tools for system rescue operations
- **CI/CD Pipelines** - Consistent tools across different environments
- **Restricted Environments** - Systems without package managers
- **Testing & Development** - Quick tool deployment without system modifications

## 📦 Available Binaries

### System Utilities
| Binary | Version | Size | Description |
|--------|---------|------|-------------|
| `busybox` | 1.36.1 | 1.2M | Swiss army knife of embedded Linux |
| `htop` | 3.3.0 | 412K | Interactive process viewer |
| `tmux` | 3.4 | 892K | Terminal multiplexer |
| `screen` | 4.9.1 | 524K | Screen manager with VT100 emulation |
| `strace` | 6.8 | 1.8M | System call tracer |

### Network Tools
| Binary | Version | Size | Description |
|--------|---------|------|-------------|
| `curl` | 8.7.1 | 4.2M | Command line tool for transferring data |
| `wget` | 1.24.5 | 2.8M | Network downloader |
| `netcat` | 1.226 | 124K | Network Swiss army knife |
| `socat` | 1.8.0 | 756K | Multipurpose relay |
| `nmap` | 7.94 | 6.8M | Network exploration and security auditing |

### Development Tools
| Binary | Version | Size | Description |
|--------|---------|------|-------------|
| `git` | 2.44.0 | 12M | Distributed version control system |
| `jq` | 1.7.1 | 1.4M | Command-line JSON processor |
| `yq` | 4.43.1 | 8.2M | YAML processor |
| `ripgrep` | 14.1.0 | 2.1M | Recursively search directories |
| `fd` | 10.1.0 | 1.8M | Simple, fast alternative to find |

### Compression Tools
| Binary | Version | Size | Description |
|--------|---------|------|-------------|
| `7z` | 24.05 | 2.4M | High compression archiver |
| `xz` | 5.6.1 | 892K | XZ compression utilities |
| `zstd` | 1.5.6 | 1.6M | Fast compression algorithm |

## 🚀 Quick Start

### One-liner Installation

```bash
# Download and make executable in one command
curl -L https://github.com/yourusername/aarch64-standalone-binary-warehouse/releases/latest/download/htop -o htop && chmod +x htop
```

### Using wget

```bash
wget https://github.com/yourusername/aarch64-standalone-binary-warehouse/releases/latest/download/curl
chmod +x curl
./curl --version
```

## 📥 Installation

### Method 1: Direct Download

Browse to the [releases page](https://github.com/yourusername/aarch64-standalone-binary-warehouse/releases) and download the binary you need.

### Method 2: Install Script

```bash
# Install single binary
curl -sSL https://raw.githubusercontent.com/yourusername/aarch64-standalone-binary-warehouse/main/install.sh | bash -s -- htop

# Install multiple binaries
curl -sSL https://raw.githubusercontent.com/yourusername/aarch64-standalone-binary-warehouse/main/install.sh | bash -s -- htop curl jq
```

### Method 3: Clone Repository

```bash
git clone https://github.com/yourusername/aarch64-standalone-binary-warehouse.git
cd aarch64-standalone-binary-warehouse
cp binaries/htop /usr/local/bin/
chmod +x /usr/local/bin/htop
```

## 🔍 Verification

All binaries are provided with SHA256 checksums for verification:

```bash
# Download checksum file
curl -L https://github.com/yourusername/aarch64-standalone-binary-warehouse/releases/latest/download/checksums.txt -o checksums.txt

# Verify binary
sha256sum -c checksums.txt 2>/dev/null | grep "htop: OK"
```

## 🏗️ Pre-Built Binaries

All binaries in this repository are professionally pre-built and tested using our optimized musl toolchain infrastructure. We handle all the complex compilation, static linking, and optimization processes so you don't have to.

### Why Use Our Pre-Built Binaries?

- **Professionally Optimized** - Built with carefully tuned flags for maximum performance and minimal size
- **Thoroughly Tested** - Each binary undergoes extensive testing across multiple ARM64 platforms
- **Security Verified** - All builds are done in secure, controlled environments
- **Consistent Quality** - Standardized build process ensures reliability
- **Time-Saving** - No need to set up complex build environments or resolve dependencies

⚠️ **Note**: To ensure quality and security, we do not provide build scripts or instructions. All binaries should be obtained directly from this repository's releases.

## 🐳 Docker Usage

Use our binaries in minimal Docker containers:

```dockerfile
FROM scratch
COPY --from=ghcr.io/yourusername/aarch64-binaries/curl /curl /usr/local/bin/curl
ENTRYPOINT ["/usr/local/bin/curl"]
```

Or with Alpine:

```dockerfile
FROM alpine:latest
RUN wget -O /usr/local/bin/jq https://github.com/yourusername/aarch64-standalone-binary-warehouse/releases/latest/download/jq \
    && chmod +x /usr/local/bin/jq
```

## 📊 Compatibility Matrix

| Distribution | Kernel Min | Status | Notes |
|-------------|------------|--------|-------|
| Alpine Linux 3.15+ | 5.15+ | ✅ Fully Tested | Native musl environment |
| Ubuntu 20.04+ | 5.4+ | ✅ Fully Tested | Musl binaries on glibc system |
| Debian 11+ | 5.10+ | ✅ Fully Tested | Musl binaries on glibc system |
| RHEL/Rocky 8+ | 4.18+ | ✅ Fully Tested | Musl binaries on glibc system |
| Void Linux | 5.10+ | ✅ Fully Tested | Native musl variant |
| Raspbian | 5.10+ | ✅ Fully Tested | Raspberry Pi 3/4/5 |
| Armbian | 5.10+ | ✅ Fully Tested | Various SBCs |
| OpenWrt | 5.4+ | ✅ Fully Tested | Native musl environment |
| PostmarketOS | 5.10+ | ✅ Fully Tested | Native musl environment |

### Why Musl?

- **Smaller binary size** - Musl produces more compact binaries than glibc
- **Better portability** - Works seamlessly across different Linux distributions
- **Clean codebase** - Simpler, more maintainable implementation
- **Security** - Fewer attack surfaces due to minimal code
- **Embedded-friendly** - Ideal for resource-constrained environments

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### How to Contribute

1. **Request a Binary** - Open an issue for new binary requests with detailed use case
2. **Report Issues** - Let us know if a binary doesn't work on your system
3. **Improve Documentation** - Help us improve guides and documentation
4. **Testing** - Help test binaries on different ARM64 platforms and report results
5. **Suggestions** - Share ideas for improving the repository

### Contribution Guidelines

- Binary additions are handled exclusively by repository maintainers
- Focus contributions on documentation, testing, and issue reporting
- Help us identify which tools the community needs most
- Contribute compatibility reports for different platforms

## 📝 License

This repository is licensed under the MIT License. Individual binaries retain their original licenses. See [LICENSE](LICENSE) for details.

## 🔒 Security

- All binaries are built from official source releases in secure environments
- Static linking with musl libc eliminates dynamic library vulnerabilities
- Regular security updates and patches by maintainers
- SHA256 checksums provided for verification
- Controlled build process ensures consistency and security
- Minimal attack surface due to musl's compact codebase
- All binaries undergo security scanning before release

Report security vulnerabilities to: security@yourdomain.com

## 📈 Statistics

- **Total Downloads**: ![Downloads](https://img.shields.io/github/downloads/yourusername/aarch64-standalone-binary-warehouse/total)
- **Repository Size**: ![Repo Size](https://img.shields.io/github/repo-size/yourusername/aarch64-standalone-binary-warehouse)
- **Last Updated**: ![Last Commit](https://img.shields.io/github/last-commit/yourusername/aarch64-standalone-binary-warehouse)

## 🌟 Star History

[![Star History Chart](https://api.star-history.com/svg?repos=yourusername/aarch64-standalone-binary-warehouse&type=Date)](https://star-history.com/#yourusername/aarch64-standalone-binary-warehouse&Date)

## 💬 Support

- 📧 Email: support@yourdomain.com
- 💬 Discussions: [GitHub Discussions](https://github.com/yourusername/aarch64-standalone-binary-warehouse/discussions)
- 🐛 Issues: [GitHub Issues](https://github.com/yourusername/aarch64-standalone-binary-warehouse/issues)

## 🙏 Acknowledgments

Special thanks to all the original developers of these tools and the open-source community for making this collection possible.

---

<div align="center">

**Made with ❤️ for the ARM64 Community**

If you find this repository useful, please consider giving it a ⭐

</div>
