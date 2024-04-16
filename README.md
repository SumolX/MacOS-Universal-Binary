# MacOS-Universal-Binary
This readme provides instructions on how to setup your macOS development environment in order to create Universal Binaries for both the Intel and Apple Silicon.

## Install Homebrew (Apple Silicon)
Installer will automatically execute.

Target Path: /opt/homebrew
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Install Homebrew (Intel Processor)
Three step process is required for setting up Intel homebrew on Apple Silicon.

Target Path: /usr/local/homebrew
### Download Homebrew
Extract homebrew tarball contents
```
mkdir homebrew
curl -L https://github.com/Homebrew/brew/tarball/master | tar xz --strip 1 -C homebrew
```
### Relocate Homebrew
Move to standard homebrew Intel path
```
sudo mv homebrew /usr/local/
```
### Update Shell Environment
Add Intel Homebrew alias to .zshrc [Append to End-of-File]
```
# Intel homebrew variant
alias axbrew='arch -x86_64 /usr/local/homebrew/bin/brew'
```

# Conclusion
Both Homebrew package managers can co-exist.  However, you must manual maintain synchronization between each installation in order to create a Universal Binary containing support for both Intel and Apple Silicon processors.
```
brew install libpng
axbrew install libpng
```
