# SOP: Fixing GitHub Remote and Push Issues

## Problem
You may see errors like:
- `remote origin already exists`
- `Permission to ... denied`
- `fatal: unable to access ... 403`

This usually means the repository is still connected to the wrong GitHub remote.

## Goal
Move the repository to the correct GitHub repository and push the code successfully.

## Steps

1. Check the current remote
```bash
git remote -v
```

2. If `origin` already exists, update it instead of adding it again
```bash
git remote set-url origin git@github.com:inhochoiotaris/mycode.git
```

3. Verify the remote was changed
```bash
git remote -v
```

4. Push the branch to GitHub
```bash
git push -u origin main
```

## If Git asks for authentication
Use SSH instead of HTTPS if your GitHub account is configured for SSH.

Check whether SSH is working:
```bash
ssh -T git@github.com
```

If needed, generate a new SSH key and add it to GitHub.

## Common Notes
- Do not run `git remote add origin ...` if `origin` already exists.
- Use `git remote set-url origin ...` to change the existing remote.
- If the repo already has commits and the branch is clean, a push will work once the remote is corrected.

## Quick Reference
```bash
git remote -v
git remote set-url origin git@github.com:inhochoiotaris/mycode.git
git push -u origin main
```
