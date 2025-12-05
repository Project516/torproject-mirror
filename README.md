# Tor Browser Mirror

Automated GitHub mirror for the latest Tor Browser releases across all platforms.

## Features

- **Automatic Updates**: Fetches the latest Tor Browser releases daily at midnight UTC
- **Single "latest" Release**: Always maintains one GitHub release tagged as "latest" that gets overwritten with each update
- **Multi-Platform Support**: Mirrors stable releases and nightly builds for:
  - Windows (x86_64 and i686 portable)
  - macOS (Universal - Intel and Apple Silicon)
  - Linux (x86_64, i686, and aarch64)
  - Android (aarch64, armv7, x86_64, x86)
  - iOS (Onion Browser)
- **Nightly Builds**: Includes latest nightly builds for all major platforms (excluding Mullvad browser)
- **Static Download Page**: Simple HTML page for easy downloads at [https://project516.github.io/tor-mirror/](https://project516.github.io/torproject-mirror/)

## Usage

Visit the [Releases](https://github.com/Project516/tor-mirror/releases/latest) page or the [download page](https://project516.github.io/torproject-mirror/) to get the latest Tor Browser for your platform.

## How It Works

1. A GitHub Actions workflow runs daily at midnight UTC
2. It fetches the latest stable Tor Browser version from `https://dist.torproject.org/torbrowser/`
3. Downloads all platform-specific stable installers
4. Downloads the latest nightly builds for all platforms from `https://nightlies.tbb.torproject.org/nightly-builds/tor-browser-builds/` (date-based URL)
5. Downloads Onion Browser for iOS from `https://github.com/OnionBrowser/OnionBrowser/releases/latest/`
6. Deletes the existing "latest" release
7. Creates a new "latest" release with all the downloaded files
8. Updates the `index.html` page with version information

## Manual Trigger

You can manually trigger the mirror update from the [Actions](https://github.com/Project516/tor-mirror/actions) tab.

## Disclaimer

This is an **unofficial mirror** of Tor Browser releases. For official releases and more information, please visit [torproject.org](https://www.torproject.org/download/).

## License

See [LICENSE](LICENSE) file for details.
