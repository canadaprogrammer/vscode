# Using Git

## Git Configuration

- Default VS Code as the git editor

  - `git config --global core.editor "code --wait"`
  - unset: `git config --global --unset core.editor`

- Set new line on editor (related to carriage-return)

  - windows: `git config --global core.autocrlf true`
  - mac: `git config --global core.autocrlf input`

- Set short key

  - `git config --global alias.st status` : `git st` instead of `git status`

- Edit git configuration
  - `get config --global -e`
  ```
  [diff]
    tool = vscode
  [difftool "vscode"]
    cmd = code --wait --diff $LOCAL $REMOTE
  ```

## Adding new SSH on GitHub

1. Create a new SSH key

- `ssh-keygen -t ed25519 -C "your_email@example.com"`

2. Add the SSH key to the ssh-agent

- Ensure the ssh-agent is running
- `eval "$(ssh-agent -s)"`
- the result will be like `Agent pid 59566` if it's running
- Add your SSH private key to the ssh-agent
- `ssh-add ~/.ssh/id_ed25519`

3. Add the SSH key to your account on GitHub

- Copy the SSH public key to your clipboard
- `clip < ~/.ssh/id_ed25519.pub`
  1. In the upper-right corner of any page, click your profile photo
  2. Click Settings
  3. Click SSH and GPG keys
  4. Click New SSH key
  5. Paste your key into the "key" field

## Connecting Git Repository with a project

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

### Solving fatal: refusing to merge unrelated histories

- This error occurs when two unrelated projects are merged into a single branch.

- The solution is `git pull origin master --allow-unrelated-histories`

## Removing commits (Undoing committed changes)

- The last commit
  - `git reset --hard HEAD^`
  - `git push origin -f`
- The last two commits
  - `git reset --hard HEAD~2`
- The last commit, but keeping the last changed
  - `git reset HEAD^`

### Solving error: failed to push some refs

- It's happened when I did `git push origin master` after `git reset HEAD~2` for keeping the last changed.
- When I did `git push origin -f`, it returned `fatal: The current branch master has no upstream branch.`

- The solution
  1. Commit
  2. `git pull origin master`
  3. Merge the changed on files by 'Accept Current Change'
  4. Commit

## undoing uncommitted changes

- Discard all untracked files, as well as staged and unstaged modifications
  - `git stash`
- Discard changes to a file permanently
  - `git checkout --<file>`
