
## 1. I have been making changes locally in branch A, but I want to leave it to work on another thing in another branch B then come back to Branch A. I have not add and commit the changes on branch B. Note I don't want changes from branch A in branch B, How do I return to branch A.
### Solution 1
#### Option 1
```js
// Stash Your Changes
git stash push -m "Work in progress on branch A"
git checkout B

```
This will:
- Save your uncommitted changes in a temporary stash.
- Switch you to branch B with a clean working directory.
When you're ready to return to branch A:
```js
git checkout A
git stash pop
```
####  Option 2: Commit to a Temporary Branch
If you want to keep your changes visible and versioned:
```js
git checkout -b temp-A-work
git add .
git commit -m "Temp commit before switching"
git checkout B

```

🕒 Duration of Git Stash
There’s no expiration by default. Your stashed changes will remain in your stash list indefinitely until you
