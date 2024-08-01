# -VHostFuzzer

VHostHunter is a simple Bash script that uses the `ffuf` tool to fuzz virtual hosts (vhosts) on a target domain. This tool is especially useful for penetration testers and security researchers who need to discover hidden vhosts using a specified wordlist.

## Features

- **Easy to use**: Simple command-line interface.
- **Customizable**: Allows specification of domain, wordlist, URL, and file size filter.
- **Fast and Efficient**: Utilizes `ffuf` for high-speed fuzzing.

## Requirements

- `ffuf` installed on your system.
- Bash shell environment.

## Installation

To install `ffuf`, use the following commands:

```bash
go get -u github.com/ffuf/ffuf
```

Ensure that your `GOPATH/bin` is in your PATH, or move the binary to a directory that is.

## Usage

Run VHostHunter with the following command:

```bash
./VHostHunter.sh <DOMAIN> <WORDLIST> <URL> <FS Filter>
```

### Arguments

- `<DOMAIN>`: The base domain to fuzz (e.g., example.com).
- `<WORDLIST>`: The file path to the wordlist containing subdomains to test.
- `<URL>`: The URL template with a placeholder for the fuzzed subdomain (e.g., http://FUZZ.example.com).
- `<FS Filter>`: The file size filter to exclude certain responses (e.g., `4242` to exclude responses of size 4242 bytes).

### Example

```bash
./VHostHunter.sh example.com subdomains.txt http://FUZZ.example.com 4242
```

This command will use `ffuf` to fuzz the `example.com` domain with subdomains from `subdomains.txt`, checking the URL structure `http://FUZZ.example.com` and excluding responses of size 4242 bytes.

## License

VHostHunter is released under No License.

## Disclaimer

This tool is intended for educational and lawful purposes only. The author is not responsible for any misuse or damage caused by using this tool.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request for any features, bug fixes, or improvements.

## Contact

For any questions or feedback, please contact Sankalp at sankalp247365@outlook.com
```
