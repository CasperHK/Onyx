# Onyx
> **A lightning-fast, native, and memory-safe Linux file manager built in Rust.**

`rfast` is designed from the ground up for Linux power users who demand zero-latency performance, low memory overhead, and deep integration with the Linux kernel. By leveraging Rust, modern asynchronous I/O, and direct system calls, `rfast` eliminates the bloat and sluggishness typical of modern file managers.

---

## ⚡ Core Features

* **Blazing Fast Directory Traversal**: Utilizes low-level system calls (`getdents64`) and multi-threading (`rayon`) to scan large directories and thousands of small files instantly.
* **Zero-Overhead Memory Footprint**: Written in pure Rust with zero garbage collection pauses, keeping memory usage to a bare minimum.
* **Real-time File System Watcher**: Powered by Linux `inotify` via `notify` for instant, event-driven UI updates without polling overhead.
* **Embedded SQLite Indexing**: Background indexing with SQLite and FTS5 enables lightning-fast global file name and metadata search.
* **Native Linux Stack**: Optimized for Wayland and X11 environments, delivering smooth interactions without heavyweight browser runtimes.

---

## 🛠️ Tech Stack

* **Language**: Rust (`edition 2024`)
* **Async Runtime**: `tokio`
* **File System Events**: `inotify` / `notify`
* **Parallelism**: `rayon`
* **Database / Indexing**: `rusqlite` (with FTS5 support)
* **CLI & Arguments**: `clap`

---

## 🚀 Getting Started

### Prerequisites

Ensure you have the latest stable Rust toolchain installed:

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

```

### Installation

Clone the repository and build in release mode for maximum performance optimization:

```bash
git clone https://github.com/your-username/rfast.git
cd rfast
cargo build --release

```

The compiled binary will be available at `target/release/rfast`.

---

## 💻 Usage

Run `rfast` directly in your terminal or specify a target directory:

```bash
# Open current directory
./target/release/rfast

# Open a specific path
./target/release/rfast /var/log

```

---

## 🗺️ Roadmap

* [ ] **Phase 1 (Core Engine)**: High-performance asynchronous VFS abstraction and parallel directory scanner.
* [ ] **Phase 2 (Watcher & Indexer)**: Integration of `inotify` event loop and SQLite background metadata caching.
* [ ] **Phase 3 (Interface)**: Native GUI rendering (via `Iced` or `Ratatui` TUI integration).
* [ ] **Phase 4 (Advanced Features)**: QuickLook-style instant file previews and Vim-like keybindings.

---

## 📄 License

This project is open-source under the [MIT License](https://www.google.com/search?q=LICENSE&utm_source=gemini).
