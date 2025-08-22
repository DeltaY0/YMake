# YMake

**YMake** is a simple, lightweight build tool for C and C++ projects, written in C++. Its goal is to provide an easy-to-use and fast alternative to more complex build systems.

## Features

- **Simple syntax:** Easy to set up and configure for small to medium C/C++ projects.
- **Cross-platform:** Designed to work on major operating systems.
- **Written in C++:** Fast, with minimal overhead.
- **Supports SWIG:** Enables C/C++ projects with SWIG interfaces.
- **Python Integration:** (if applicable, based on repo composition)
- **Highly customizable via TOML:** Build configuration is managed through a TOML file, with practical examples in the `YMakeTests` directory.

## Getting Started

### Prerequisites

- C++ compiler (GCC, Clang, MSVC, etc.)
- [SWIG](http://www.swig.org/) (if using SWIG interfaces)
- (Optional) Python 3.x if integrating Python modules

### Building YMake

Clone the repository:

```bash
git clone https://github.com/DeltaY0/YMake.git
cd YMake
```

Build using the provided scripts for your platform:

- On **Windows**:
  ```bat
  build.bat
  ```
- On **Linux/macOS**:
  ```sh
  ./build.sh
  ```

### Usage

Basic usage example:

```bash
./ymake [options] [target]
```

- Use `-h` or `--help` to see available options.
- Use `-v` or `--version` to show version information.

#### Project Configuration

YMake uses a **TOML configuration file** to define build targets and settings.  
**You can find practical and advanced TOML configuration examples in the [`YMakeTests`](./YMakeTests) directory.**  
Customize your build process by editing this TOML file to suit your project's needs.

### Example

Suppose you have a simple C++ project with a `ymake.toml` in your root directory:

```bash
./ymake build
```

#### Sample TOML Configuration

Below is an example TOML configuration file (as found in a typical project within `YMakeTests`):

```toml
[project]
name = "SampleProject"
version = "1.0"

[build]
sources = ["main.cpp", "utils.cpp"]
include_dirs = ["include"]
cflags = ["-O2", "-Wall"]
ldflags = []
output = "sample_project"

[[target]]
name = "run"
cmd = "./sample_project"
```

**How to use it:**

1. Place the TOML configuration file (e.g., `ymake.toml`) in your project root.
2. Edit the `[project]` section to specify your project's name and version.
3. List your source files and include directories under `[build]`.
4. Optionally, add custom compiler (`cflags`) and linker flags (`ldflags`).
5. Specify the output binary name with `output`.
6. Define custom build or run targets under `[[target]]` as needed.
7. Run `./ymake build` to build your project according to this configuration.
8. Execute custom targets (like `run`) using `./ymake run`.

For more complex configurations, refer to the examples in `YMakeTests`.

## Directory Structure

- `src/` — Main source code
- `YMakeTests/` — Example TOML build files and test projects
- `scripts/` — Helper scripts for building or installing (if available)

## Contributing

Contributions, issues, and feature requests are welcome!  
Feel free to check the [issues page](https://github.com/DeltaY0/YMake/issues) to get started.

1. Fork this repository
2. Create your feature branch: `git checkout -b my-feature`
3. Commit your changes
4. Push to the branch: `git push origin my-feature`
5. Open a pull request

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Authors

- [DeltaY0](https://github.com/DeltaY0)

---

**YMake** — Simple C/C++ Build Tool