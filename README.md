# BFFUF

**BFFUF** is a simple Bash script designed to act as a wrapper for the powerful web fuzzer, **Ffuf**. It streamlines common reconnaissance tasks by providing an easy-to-use command-line interface for directory, virtual host, and DNS subdomain brute-forcing.

---

## Features

* **Mode-Based Fuzzing**: Choose from `dir`, `vhost`, or `dns` modes to quickly set up your fuzzing task.
* **Flexible Protocol Handling**: Automatically detects and uses the correct protocol (`http` or `https`) from the target URL.
* **Dynamic Domain Extraction**: Intelligently extracts the base domain from a URL for use in virtual host and DNS enumeration.
* **Pass-Through Flags**: Any additional Ffuf flags you provide are automatically passed to the underlying command.

---

## Usage

```bash
./bffuf <mode> <url/domain> <wordlist> [ffuf_flags]
```

### Examples:

1.  **Directory Fuzzing** (`dir`)
    ```bash
    ./bffuf dir https://example.com/ /usr/share/wordlists/dirb/common.txt -fc 404
    ```

2.  **Virtual Host Fuzzing** (`vhost`)
    ```bash
    ./bffuf vhost https://example.com/ /usr/share/wordlists/dirbuster/dns-Jhaddix.txt -H "X-Forwarded-For: 127.0.0.1"
    ```

3.  **DNS Subdomain Fuzzing** (`dns`)
    ```bash
    ./bffuf dns http://example.com/ /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-110000.txt -fc 403,404
    ```

---

## Dependencies

* **Bash**: This script requires a Bash-compatible shell.
* **Ffuf**: You must have the `ffuf` tool installed and available in your system's PATH.

---

## Credits

This script is a wrapper for the excellent work of the Ffuf team. A huge thanks to them for creating and maintaining such a powerful and versatile tool.

**Ffuf Project**: [ffuf/ffuf: Fast web fuzzer written in Go](https://github.com/ffuf/ffuf)
