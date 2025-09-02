# Buji Code Homebrew Tap

This repository contains Homebrew formulae for [Buji Code](https://github.com/buji-code) tools.

## Install

First, add this tap to your Homebrew installation:

```bash
brew tap buji-code/tap
```

Then install any of the available tools:

```bash
# Install flags-gen - Go code generator for command-line flag parsers
brew install flags-gen
```

## Available Tools

### flags-gen
A Go code generator that creates command-line flag parsers from struct definitions with annotations.

**Features:**
- Generate flag parsers from Go structs
- Support for various data types (string, int, bool, slices, time.Duration)
- Automatic kebab-case flag naming from struct fields
- JSON tag support for custom flag names
- Default value support via struct tags
- Comprehensive field descriptions from comments

**Usage:**
```bash
# Generate flags for a Go file
flags-gen -i input.go -o output.go

# Show version
flags-gen version

# Show help
flags-gen --help
```

**Example:**
```go
// +flags-gen
type Config struct {
    Port     int           `json:"port" default:"8080"`
    Host     string        `json:"host" default:"localhost"`
    Debug    bool          `json:"debug"`
    Timeout  time.Duration `json:"timeout" default:"30s"`
}
```

Generates a complete flag parser with `--port`, `--host`, `--debug`, and `--timeout` flags.

## Repository Information

- **Homepage:** https://github.com/buji-code/flags-gen
- **Issues:** https://github.com/buji-code/flags-gen/issues
- **Releases:** https://github.com/buji-code/flags-gen/releases

## Contributing

If you have issues with any of the formulae, please report them on the respective tool's GitHub repository.

## Manual Installation Alternatives

If you prefer not to use Homebrew, you can also install tools via:

### Go Install
```bash
go install github.com/buji-code/flags-gen/cmd/flags-gen@latest
```

### Direct Binary Download
Download pre-compiled binaries from the [releases page](https://github.com/buji-code/flags-gen/releases).

### Docker
```bash
docker run ghcr.io/buji-code/flags-gen:latest --help
```