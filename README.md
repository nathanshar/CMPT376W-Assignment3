# LogLens v1.0

LogLens is a command-line Python tool that counts the records in CSV log files. LogLens lets users run commands to count all records or filter records by a specific log level.

LogLens is designed for undergraduate computing students and new technical interns with basic knowledge of terminal commands and CSV files.

LogLens processes files locally; it does not modify, repair, or upload input files, and it doesn't diagnose system failures.

## Requirements

- Python 3.10 or newer
- CSV file containing the required column headers
- Basic familiarity with terminal commands and CSV files
- Third-party dependencies and package installation are not required

## Getting Started

1. Download and extract the project files from this GitHub repository.
2. Open a terminal and navigate to the repository root (folder containing `loglens.py`).
3. Follow the [Installation and Setup Guide](docs/INSTALL.md) for detailed instructions.

## Usage

From the repository root, run the following commands.

### Count records by log level

To count records with the `ERROR` log level in the provided sample file, run:

```bash
python loglens.py --file data/sample_logs.csv --level ERROR
```

Expected output:

```text
Records matching ERROR: 2
```

### Count all records

To count all records without filtering by log level, run:

```bash
python loglens.py --file data/sample_logs.csv
```

Expected output:

```text
Records matching ALL: 6
```

### Command-line arguments


| Argument  | Required | Description                                                                         |
| --------- | -------- | ----------------------------------------------------------------------------------- |
| `--file`  | Yes      | Specifies the path to the input CSV file.                                           |
| `--level` | No       | Filters records by `INFO`, `WARN`, or `ERROR`. If omitted, all records are counted. |
| `--help`  | No       | Displays available command-line options.                                            |


To view the available options, run:

```bash
python loglens.py --help
```

**Note:** Depending on the computer in use, you may need to replace `python` with `python3` or `py`.

## CSV Input Format

The input CSV file must contain the following exact column headers:


| Column      | Description                                |
| ----------- | ------------------------------------------ |
| `timestamp` | The recorded time of the log entry.        |
| `level`     | The log level: `INFO`, `WARN`, or `ERROR`. |
| `message`   | The message associated with the log entry. |

 
Log levels must be in uppercase.

A verified example is available in the [sample CSV file](data/sample_logs.csv).

To use your own CSV file, replace `data/sample_logs.csv` in the example with the path to your file.

## Troubleshooting and Support

For setup instructions and common problems, refer to the [Installation and Setup Guide](docs/INSTALL.md).

If you encounter an unresolved problem, describe the issue in a GitHub issue and provide a sanitized, minimal example when necessary.

**Privacy warning:** Do not publicly share original log files containing personal, confidential, or any sensitive information.
