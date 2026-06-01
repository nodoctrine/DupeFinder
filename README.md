# Dupe Finder

> **What it is:** A single HTML file that scans a local folder for duplicate files and displays results in the browser.
> **Last Updated:** June 2026

---

## How it works

Select a folder using the file picker or drag one onto the drop zone. The tool reads every file in that folder, including subfolders, and computes a SHA-256 hash for each one. Files with matching hashes are identical in content regardless of name or location.

Nothing leaves your machine. All processing runs locally in the browser.

---

## Size pre-filter

Before hashing, files are grouped by size. Two files of different sizes cannot be identical, so any file with a unique size is skipped. This cuts down hashing work significantly on large folders.

---

## Output

After a scan, results appear in three collapsible sections:

**Directory Analysis** shows pairs of directories that share more than one duplicate file. Pairs where nearly all files overlap are flagged with a warning badge. Single-file matches between directories are excluded.

**File Size Analysis** lists every duplicate group, sorted by wasted space. Each group shows the filename, file size, copy count, and total wasted space. Click a group header to expand it and see the full path for each copy.

**Filter** - use the filter input in the controls bar to narrow results by filename or path. Filtering applies to the file list in real time.

---

## Themes

Four themes are available via the bar at the top: Dark, Terminal, Y2K, and Light. The Terminal theme replaces the visual UI with a command-line interface. Available commands are listed by typing `help`.

---

## Export

The **Export CSV** button downloads a file with one row per duplicate. Columns: hash, filename, full path, size in bytes, copy count.

---

## Notes

> **Note:** Files under 1 byte are ignored.
> **Note:** Drag-and-drop folder support depends on the browser. The file picker (`webkitdirectory`) works in Chrome, Firefox, and Edge.

>/__!__\ WARNING /__!__\
>SHA-256 hashing large files (several hundred MB or more) will block the browser tab temporarily. The tool yields to the UI every 20 files, but very large individual files will still cause a brief freeze.
