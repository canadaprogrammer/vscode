# Add new SSH on GitHub

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
