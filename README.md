# Automatic File Sorting using Python (os + shutil)

This project automatically sorts files in a specified folder (like Downloads or Desktop) into subfolders based on their file types — for example, moving `.csv` files to a "csv files" folder, `.pptx` files to a "ppt file" folder, `.mov` files to a "mov file" folder, and so on.

## Overview
The script uses Python’s built-in **os** and **shutil** modules to:
- Scan all files in a directory
- Check file extensions
- Automatically move them into their respective folders
- Prevent duplicates by checking if the file already exists before moving

This is a simple automation that helps keep your file explorer organized.

## Features
- Automatically detects and sorts files by type  
- Creates folders for each file type if they don’t exist  
- Skips files already sorted  
- Works on macOS, Windows, and Linux  

## Technologies Used
- **Python 3**
- **os** module – for reading directories and checking paths  
- **shutil** module – for moving files  

## Example File Types Handled
- `.csv` → moved to **csv files/**
- `.ppt` / `.pptx` → moved to **ppt file/**
- `.mov` → moved to **mov file/**
- `.heic` → moved to **heic file/**

## Code Example
```python
import os
import shutil

path = r"/Users/rohita/file_sorting_files/"
file_name = os.listdir(path)

for file in file_name:
    if ".csv" in file and not os.path.exists(path + "csv files/" + file):
        shutil.move(path + file, path + "csv files/" + file)
    if ".ppt" in file and not os.path.exists(path + "ppt file/" + file):
        shutil.move(path + file, path + "ppt file/" + file)
    if ".mov" in file.lower() and not os.path.exists(path + "mov file/" + file):
        shutil.move(path + file, path + "mov file/" + file)
    if ".heic" in file.lower() and not os.path.exists(path + "heic file/" + file):
        shutil.move(path + file, path + "heic file/" + file)
