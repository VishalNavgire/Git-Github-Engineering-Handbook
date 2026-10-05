# 🧬 Git Objects (Under the Hood)

*(Deep dive into how Commits from [06-Commits-and-Commit-History](06-Commits-and-Commit-History.md) are actually stored)*

Git is a **content-addressable filesystem**. Instead of tracking files by their names, Git tracks them by calculating a mathematical hash (SHA-1) of their content.

Inside the `.git/objects` folder, everything is stored as one of three core primitive objects:

### 1. Blobs (Files)
*   Stands for **B**inary **L**arge **Ob**ject.
*   Stores *only* the file's content. It does not store the file name.

### 2. Trees (Directories)
*   Stores the structure of your folders.
*   Contains pointers to Blobs (files) and other Trees (sub-folders), mapping them to human-readable filenames.

### 3. Commits (Snapshots)
*   Points to a single, top-level Tree object representing the root directory of your project at that exact moment.

### Why This Matters for Troubleshooting
If you rename a file without changing its content, Git doesn't create a new Blob. It just updates the Tree to point the new filename to the exact same Blob. This makes Git incredibly fast and efficient.