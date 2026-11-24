# LogLens v1.0 Installation and Setup Guide

This guide explains how to obtain, set up, and run LogLens for the first time. This guide assumes you're familiar with CSV files and terminal commands.

For an overview of LogLens and its features, see the [README](../README.md).

## 1. Check the Requirements

Before starting, ensure that you have:

- Python 3.10 or newer.
- Access to a terminal.
- The LogLens project files.

Check your Python version by running:

```bash
python --version
```

If the `python` command is not recognized, try `python3` or `py`. Use the working command throughout this guide.

LogLens uses only the Python standard library. It does not use `pip install` commands or any third-party dependencies.

## 2. Obtain the Project Files

1. Open the LogLens GitHub repository.
2. Select **Code**, then **Download ZIP**.
3. Extract the downloaded ZIP file.
4. Open a terminal.
5. Navigate to the extracted repository folder using the `cd` command.

The repository root is the folder containing `loglens.py`.

Before continuing, locate the following files:

- `loglens.py` — the Python script.
- `data/sample_logs.csv` — the sample CSV file.
- `README.md` — the project overview/usage reference.

LogLens can run directly from the repository root without additional installation.

## 3. Verify That LogLens Works

From the repository root, run:

```bash
python loglens.py --file data/sample_logs.csv
```

Expected output:

```text
Records matching ALL: 6
```

Next, verify that filtering by log level works:

```bash
python loglens.py --file data/sample_logs.csv --level ERROR
```

Expected output:

```text
Records matching ERROR: 2
```

If both commands produce the expected results, LogLens is ready to be used.

## 4. Use Your Own CSV File

Your CSV file must contain the following exact column headers:

- `timestamp`
- `level`
- `message`

The accepted log levels are `INFO`, `WARN`, and `ERROR`. These values must be uppercase.

Replace `data/sample_logs.csv` in the example commands with the path to your own CSV file. Enclose the file path in quotation marks if it contains spaces.

The `--file` argument is required. The `--level` argument is optional. Omitting `--level` counts all records.

For a reference CSV file, see the [sample log data](../data/sample_logs.csv).

To view the available command-line options, run:

```bash
python loglens.py --help
```

## 5. Troubleshooting

| Problem | Recommended solution |
| --- | --- |
| Python command is not recognized | Try `python3` or `py` instead of `python`. |
| Python version is below 3.10 | Use Python 3.10 or newer. |
| File not found | Verify the file path, filename, and current working directory. |
| CSV format error | Check that the CSV contains the exact required column headers. |
| Invalid log level | Use `INFO`, `WARN`, or `ERROR` in uppercase. |
| Missing or incorrect arguments | Run `python loglens.py --help` to review the available options. |
| Unexpected sample results | Confirm that you are using the provided sample CSV and the correct command. |

## 6. Privacy and Support

LogLens processes CSV files locally. It will not upload, transmit, repair, or modify input files.

If a problem persists, open a GitHub issue describing the problem and the command that was attempted. Include a sanitized, minimal example if necessary.

**Privacy warning:** Never publicly attach any original log files containing personal, confidential, or sensitive information.
