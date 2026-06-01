# Dupe Finder

> **What it is:** A single HTML file that scans a local folder for duplicate files and displays them in the browser.
> **Last Updated:** June 2026

---

## How it works

Select a folder using the file picker or drag one onto the drop zone. The tool reads every file in that folder, including subfolders, and computes a SHA-256 hash for each one. Files with matching hashes are identical in content regardless of their name or location.

Results are grouped by duplicate set and sorted by wasted space - the group occupying the most redundant disk space appears first.

Nothing leaves your machine. All processing runs locally in the browser.

---

## Size pre-filter

Before hashing anything, files are grouped by size. Two files of different sizes cannot be identical, so any file with a unique size is skipped. This reduces hashing work significantly on large folders.

---

## Output

Each duplicate group shows:

- The filename
- File size
- Number of copies
- Total wasted space for that group
- Full relative path for each copy

Click a group header to expand it and see all paths. Use the filter input to search by filename or path.

---

## Export

The **Export CSV** button downloads a file with one row per duplicate, including hash, filename, full path, size in bytes, and copy count.

---

## Notes

> **Note:** Files under 1 byte are ignored.
> **Note:** Drag-and-drop folder support depends on the browser. The file picker (`webkitdirectory`) works in Firefox, Chrome, and Edge.

>/__!__\ WARNING /__!__\
>SHA-256 hashing large files (several hundred MB or more) will block the browser tab temporarily. The tool yields to the UI every 20 files, but very large individual files will still cause a brief freeze.
