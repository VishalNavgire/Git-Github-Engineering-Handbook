# 🚦 Git State and Status

*(Applying the theory from [05-Working-Tree-Staging-Area-Repository](05-Working-Tree-Staging-Area-Repository.md) to daily usage)*

The most common command you will run in Git is `git status`. It is your diagnostic dashboard, showing exactly where your files reside across the Three-State Architecture.

### Decoding File States

1.  **Untracked:** A brand new file in your Working Tree that Git has never seen before. It is not in the Staging Area or the Repository.
2.  **Modified:** A file Git already knows about, but you have made changes to it in your Working Tree since the last commit.
3.  **Staged:** A modified or untracked file that you have explicitly added to the Index (Staging Area) using `git add`. It is ready to be committed.
4.  **Unmodified:** The file in your Working Tree perfectly matches the version safely stored in the Local Repository. `git status` will ignore these files to keep the output clean.

### The Golden Rule of Status
If `git status` says "Changes to be committed", the file is in the Staging Area. 
If it says "Changes not staged for commit", the file is Modified in the Working Tree.