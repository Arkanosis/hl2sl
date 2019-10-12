# hl2sl [![Version](https://img.shields.io/badge/version-v0.1.0--dev-orange.svg)](https://semver.org/spec/v2.0.0.html) [![License](http://img.shields.io/badge/license-ISC-blue.svg)](/LICENSE)

**hl2sl** is a simple tool to transform hardlinks to symlinks for filesystems that don't support hardlinks, such as BeeGFS.

## How it works

hl2sl replaces all files with more than one hardlink to symlinks to a unique hardlink in the `.hardlinks` directory.

Hardlinks in the `.hardlinks` directory are named after their inode, so it's possible to run the script several times.

Replacement symlinks have the same modification time as the original hardlinks.

## Usage

Run `hl2sl` from the directoy to convert.

## Dependencies

hl2sl currently depends on python2 as a workaround for old distros which do not ship a recent enough version of binutils (eg. RHEL6).

Starting somewhere in 2020, as RHEL6 and python2 will both be EOL, a recent version of binutils (one which supports the `-r` flag of `ln`) will be required instead.

## Contributing and reporting bugs

Contributions are welcome through [GitHub pull requests](https://github.com/Arkanosis/hl2sl/pulls).

Please report bugs and feature requests on [GitHub issues](https://github.com/Arkanosis/hl2sl/issues).

## License

hl2sl is copyright (C) 2019 Jérémie Roquet <jroquet@arkanosis.net> and licensed under the ISC license.
