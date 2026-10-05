# Lab: Your First Git Repository

*(Putting the moodules into practice)*

We will now create a safe, disposable repository to prove the concepts we've learned, moving a file through the Three-State Architecture.

---
# Step 1: Configure Your Identity (Prerequisite)

Git requires an identity stamped onto every commit. If you don't set this, Git will block your first commit.
```text
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

```

---

# Step 2: Create the Working Tree
```text
mkdir my-first-repo
cd my-first-repo
```
---

# Step 3: Initialize the Local Repository (The Vault)

```text
git init
Note: This creates the hidden .git folder.

```
---
# Step 4: Create a File and Check State

```text
echo "Hello Git" > readme.txt

git status

Output Analysis: Git sees readme.txt as Untracked in the Working Tree. It has never seen this file before.
```
---

# Step 5: Move to the Staging Area (The Index)
```text
git add readme.txt
git status
Output Analysis: The file turns green ("Changes to be committed"). It is queued in the Staging Area.
```
---

# Step 6: Save to the Repository (Commit)
```text
git commit -m "Initial commit"

git status

Output Analysis: "working tree clean." The snapshot is permanently stored, and the Working Tree exactly matches the Repository.
```
---

# Step 7: Modify an Existing File
Now we will prove how Git tracks changes to files it already knows about.

```text
echo "Learning the Three-State Engine" >> readme.txt

git status

Output Analysis: Git now lists the file as Modified (in red) under "Changes not staged for commit".
```
---
# Step 8: Inspect the Working Tree Changes
```text
git diff

Output Analysis: Git shows exactly what changed between the Local Repository and your Working Tree (the newly added line will appear with a + symbol).
```
---
# Step 9: Stage and Commit the Modification
```text
git add readme.txt

git commit -m "Add second line to readme"
```
---

# Step 10: Verify the History Chain and Pointer
```text
git log --oneline

Output Analysis: You will now see two commit hashes. The top commit will point to HEAD -> main, proving that the main branch pointer moved forward to your newest snapshot.
```