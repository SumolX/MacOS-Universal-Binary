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

# Donation
If you enjoyed this work or would like to support my other projects please feel free to donate or join my patreon.

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif)](https://www.paypal.com/donate/?hosted_button_id=E4DSQMLR5JUXS)

[<img src="https://brandlogos.net/wp-content/uploads/2021/12/Patreon_logo_old-1536x352.png" width="88" height="20"/>](https://patreon.com/sumolx?utm_medium=unknown&utm_source=join_link&utm_campaign=creatorshare_creator&utm_content=copyLink)
