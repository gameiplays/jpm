JPM [![Dependency Status](https://david-dm.org/mozilla-jetpack/jpm.png)](https://david-dm.org/mozilla-jetpack/jpm) [![Build Status](https://travis-ci.org/mozilla-jetpack/jpm.png)](https://travis-ci.org/mozilla-jetpack/jpm)
===

[![NPM](https://nodei.co/npm/jpm.png?stars&downloads)](https://nodei.co/npm/jpm/)
[![NPM](https://nodei.co/npm-dl/jpm.png)](https://nodei.co/npm/jpm)

[Jetpack](https://wiki.mozilla.org/Jetpack) Manager for Node.js

Replacing the previous python tool for developing Firefox Add-ons, [cfx](https://developer.mozilla.org/en-US/Add-ons/SDK/Tools/cfx), jpm is a utility for developing, testing, and packaging add-ons.

**Currently only works with Firefox 38+**. Check out the `--binary` flag for ensuring that you're using the correct release of Firefox with jpm.

## Install

To install with npm, version 3.0.0 or higher is required.
Make sure you are up to date:

    npm install --global npm

Here's how to
[complete the npm upgrade](https://github.com/npm/npm/wiki/Troubleshooting#upgrading-on-windows)
on Windows.

Install the jpm module:

    npm install --global jpm


Install from GitHub to get the latest features or to work on jpm itself.
Use [npm link](https://www.npmjs.org/doc/cli/npm-link.html) to add the `jpm` global to your path:

    git clone https://github.com/mozilla-jetpack/jpm.git
    cd jpm
    npm install
    npm link

## Usage

Type `jpm --help` for all available commands and options or read the documentation linked below.

### Documentation

* [Getting Started with jpm](https://developer.mozilla.org/en-US/Add-ons/SDK/Tutorials/Getting_Started_%28jpm%29)
* [package.json keys that jpm uses](https://developer.mozilla.org/en-US/Add-ons/SDK/Tools/package_json#Key_reference)
* [Command Line Guide](https://developer.mozilla.org/en-US/Add-ons/SDK/Tools/jpm)
* [Self-hosting signed add-ons](https://developer.mozilla.org/en-US/Add-ons/SDK/Tools/jpm#Supporting_updates_for_self-hosted_add-ons)
* [Transitioning From CFX](https://developer.mozilla.org/en-US/Add-ons/SDK/Tools/cfx_to_jpm)

## Contributing

Read about [how to contribute patches](CONTRIBUTING.md) to `jpm`.

## Using Post and Watchpost

**Note: this is experimental**

### Setup

You must have the [Extension Auto-Installer](https://addons.mozilla.org/en-US/firefox/addon/autoinstaller/)
installed on a pre-production Firefox and you need to use a profile
that sets `xpinstall.signatures.required` to `false`
([more info](http://www.ghacks.net/2015/06/19/how-to-disable-the-firefox-40-add-on-signing-requirement/)). For logging with `watchpost`, also see [Developing without browser restarts](https://developer.mozilla.org/en-US/Add-ons/SDK/Tools/jpm#Developing_without_browser_restarts).

### Usage

Once this has completed, setup a watchpost:

    jpm watchpost --post-url http://localhost:8888/

This will watch for changes to the current working directory and post a new xpi to your installed
Extension Auto-Installer which will then install the new xpi.  To end the process, use the hokey, `CTRL + C`.

For a simple xpi and post, use:

    jpm post --post-url http://localhost:8888/

## License

[MPL-2.0](https://mozilla.org/MPL/2.0/)
