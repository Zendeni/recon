# Reconnaissance Script

This Bash script performs reconnaissance on specified domains using different scanning tools. It supports running in interactive mode and generates a report for each domain scanned. The script relies on a library (`scan.lib`) which should contain the implementation of the scan functions.

## Requirements

Ensure you have the following tools and libraries installed and accessible in your PATH:

- `nmap`
- `dirsearch`
- `jq`
- `crt.sh` (or an equivalent function in `scan.lib`)

## Usage

The script can be run in two modes: interactive mode and batch mode. You can also specify which scanning mode to use (`nmap-only`, `dirsearch-only`, `crt-only`, or default which runs all scans).

### Command-line Arguments

- `-m`: Specify the mode for scanning. Options are `nmap-only`, `dirsearch-only`, `crt-only`.
- `-i`: Run the script in interactive mode.

### Examples

1. **Interactive mode:**

    ```sh
    ./recon.sh -i
    ```

    In interactive mode, the script will prompt you to enter domain names one by one until you type `quit`.

2. **Batch mode with all scans:**

    ```sh
    ./recon.sh example.com test.com
    ```

    This will run all scans (`nmap`, `dirsearch`, and `crt.sh`) on `example.com` and `test.com`.

3. **Batch mode with specific scan (e.g., nmap-only):**

    ```sh
    ./recon.sh -m nmap-only example.com
    ```

    This will run only the `nmap` scan on `example.com`.

## Output

The script generates a directory for each domain scanned, containing the scan results and a consolidated report.

### Directory Structure

For a domain `example.com`, the directory structure will be as follows:

