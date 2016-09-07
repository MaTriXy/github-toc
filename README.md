## Table of Contents for GitHub

Browser extension that adds a table of contents to repositories, gists and wikis.

Available for [Google Chrome][Chrome], [Firefox][Firefox], [Safari][Safari] and as [userscript][Userscript].

![Screenshot](img/screenshots/safari1.png)

This is a simple browser extension that makes reading long files and pages on GitHub easier. If you regurlarly scroll around readmes and wikis looking for specific information, this is for you. Find what you are looking for, quickly.

Works almost anywhere on GitHub.

- Works with files in repos, gists, and wikis
- Supports any [GitHub markup](https://github.com/github/markup#markups)
- Supports editing and creating files and wiki pages directly on GitHub
- It's simple and unobtrusive

## Install

🚀 **[Chrome (Chrome Web Store)][Chrome]**

🚀 **[Firefox (Mozilla Add-Ons)][Firefox]**

🚀 **[Safari][Safari]**

🚀 **[Userscript][Userscript]**

Note on Safari: The Safari extension is not (yet) hosted on Apple's Extension Gallery. To install, [download the extension `safari.safariextz` from the `dist` folder][Safari] and open it. Since the extension is not from the Gallery, Safari will ask you to trust it.

## Build Yourself

You need [`node`](https://nodejs.org/)/[`npm`](https://www.npmjs.com/).

    # Clone or download zip file
    git clone git@github.com:arthurhammer/github-toc.git
    cd github-toc

    # Install development dependencies
    npm install

    # Build unpackaged extensions for testing and running locally
    npm run build

    # Build extensions packaged for distribution
    npm run dist

Packaged and unpackaged builds live in the [`dist`](dist/) folder. [`gulp`](http://gulpjs.com/) is used to run the tasks (installed with the other dependencies).

### Testing and Running Locally

First, build the unpackaged extensions with `npm run build`. Then, install the extensions in the browser as described below. Test it on the [cases described in the `test` folder](test/Readme.md).

#### Google Chrome

**Manually**:

- Open the extensions page in Chrome
- Choose `dist/chrome` under “Load unpacked extension...”

**Command line**:

- `npm run chrome` opens a new Chrome instance with the extension installed.

Chrome has to be closed for this to work. The path to Chrome is hard-coded, change if needed.

#### Firefox

**Manually**:

- Open `about:debugging` in Firefox
- Choose `dist/firefox/manifest.json` under "Load Temporary Add-on"

See [the documentation](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/Temporary_Installation_in_Firefox) for more.

**Command line**:

- `npm run firefox` opens a new Firefox instance with the extension installed.

This calls Mozilla's [`web-ext`][web-ext] tool. See its [documentation][web-ext] if it complains about unsigned extensions.

[web-ext]: https://developer.mozilla.org/en-US/Add-ons/WebExtensions/Getting_started_with_web-ext


#### Safari

- Open Extension Builder in Safari
- Add `dist/safari.safariextension` as existing extension
- Click “Install”

Note: Unless you have a valid Safari Extension certificate, the extension will automatically be removed whenever you quit Safari. You will also not be able to build the packaged extension for direct install. [The certificate requires a (paid) Apple Developer Program membership](https://developer.apple.com/library/safari/documentation/Tools/Conceptual/SafariExtensionGuide/ExtensionsOverview/ExtensionsOverview.html#//apple_ref/doc/uid/TP40009977-CH15-SW26).

#### Userscript

Install `dist/github-toc.user.js` directly in the browser if supported or with your favorite userscript manager (e.g. [Greasemonkey](https://addons.mozilla.org/en-US/firefox/addon/greasemonkey/) or [Tampermonkey](https://tampermonkey.net)).

## Changelog

See [CHANGELOG.md](CHANGELOG.md).


[Chrome]: https://chrome.google.com/webstore/detail/table-of-contents-for-git/hlkhpeomjgelmljaknhoboeohhgmmgcn
[Firefox]: https://addons.mozilla.org/en-US/firefox/addon/github-toc/
[Userscript]: https://github.com/arthurhammer/github-toc/raw/master/dist/github-toc.user.js
[Safari]: https://github.com/arthurhammer/github-toc/blob/master/dist/safari.safariextz?raw=true
