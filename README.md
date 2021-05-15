# Checksum

Introducing Checksum! The all-in-one command-line utility that allows you to
compute and verify message digests.

You can think of this program as the ultimate combination of the various
message digest commands offered by the GNU Coreutils project, e.g., `sha1sum`, `sha224sum`, `sha25sum`, etc.

## Installation

Please view the provided [installation file](INSTALL.md).

## Example Usage

Assume file `foo.txt` houses the words "Hello world!".

```
$ checksum foo.txt
0ba904eae8773b70c75333db4de2f3ac45a8ad4ddba1b242f0b3cfc199391dd8  foo.txt

$ checksum -c
0ba904eae8773b70c75333db4de2f3ac45a8ad4ddba1b242f0b3cfc199391dd8  foo.txt
foo.txt: OK

$ checksum -ba SHA1 foo.txt
47a013e660d408619d894b20806b1d5086aab03b *foo.txt
```

## Contribution

Please view the provided [contribution file](CONTRIBUTING.md).

## License

[GNU GPLv3+](LICENSE.md)
