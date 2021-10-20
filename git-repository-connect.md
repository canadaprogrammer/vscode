# Git Repository Connect with a project

1. `git init .` on the project folder

2. Create a repository on GitHub

- copy the SSH of the repository

3. Connect the repository

- `git remote add origin git@github.com:username/repository_name` (the SSH)
- `git remote -v` (check the connection)

4. Synchronize git history

- `git pull origin master`

5. Upload files to git repository

- ```bash
  git add .
  git commit -m 'first commit'
  git push -u origin master
  ```

## Solving fatal: refusing to merge unrelated histories

- This error occurs when two unrelated projects are merged into a single branch.

- The solution is `git pull origin master --allow-unrelated-histories`
