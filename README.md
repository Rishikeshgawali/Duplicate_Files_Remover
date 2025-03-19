# Duplicate File Remover

## Description
This Python project is designed to find and delete duplicate files within a specified directory by comparing the MD5 hashes of files. The script recursively traverses the directory, identifies duplicate files, and deletes all but one of the duplicates, freeing up disk space.

The script includes functionality for:
- Scanning a directory and identifying files with identical content.
- Displaying the list of duplicate files.
- Deleting duplicate files, keeping only one copy of each file.

## Features
- **Detect Duplicate Files**: Find duplicate files based on their content (using MD5 hashing).
- **Delete Duplicates**: Automatically delete all but one copy of each set of duplicate files.
- **Print Results**: Display the duplicate files found during the scan.
- **Cross-Platform Compatibility**: Works on any system with Python installed (Linux, macOS, Windows).

## Requirements
- Python 3.x
- No additional libraries required; uses built-in modules (`os`, `hashlib`, `time`).

## Usage

### Running the Program
To run the program, execute the following command in the terminal:

```bash
python DuplicateRemover.py /path/to/directory
```

Replace `/path/to/directory` with the absolute path of the directory you want to scan for duplicate files.

### Command-Line Arguments
- `-h` or `-H`: Displays help information about the script.
- `-u` or `-U`: Displays usage instructions.

### Example:
```bash
python DuplicateRemover.py /home/user/Documents
```

This will scan the `/home/user/Documents` directory and attempt to find and delete duplicate files based on their MD5 hashes.

## Functions in the Script

### `hashfile(path, blocksize=1024)`
Generates and returns the MD5 hash of a file given its path.

### `FindDup(path)`
Recursively scans the given directory and stores files' MD5 hashes and paths in a dictionary. Identifies files with identical hashes as duplicates.

### `DeleteFiles(dict1)`
Deletes duplicate files by checking the hash of each file. Only one copy of each set of duplicate files is kept.

### `PrintResults(dict1)`
Prints the paths of all the duplicate files found by `FindDup()`.

### `main()`
The main function that orchestrates the execution of the script. It handles the command-line arguments and calls the necessary functions.

## Example Output
When the script runs, the output will display the directory being scanned and the list of duplicate files:

### If duplicates are found:
```bash
----Program by Rishikesh Gawali----
Application name is : DuplicateRemover.py
Current folder is : /path/to/your/directory
Current folder is : /path/to/your/directory/subfolder
Duplicate Found
The following results are identical.
		/path/to/your/directory/file1.txt
		/path/to/your/directory/file1_duplicate.txt
```

### If no duplicates are found:
```bash
----Program by Rishikesh Gawali----
Application name is : DuplicateRemover.py
Current folder is : /path/to/your/directory
Current folder is : /path/to/your/directory/subfolder
No duplicate files found.
```

## Author
- **RISHIKESH BHARAT GAWALI**.
