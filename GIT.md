# Git

## Configurations
```
# The local config file is in the project directory: .git/config.

# local set
git config user.email mahmoud@company.ccc
git config user.name 'Mahmoud Zalt'

# local get
git config --get user.email
git config --get user.name

# The global config file in in your home directory: ~/.gitconfig.

# global set
git config --global user.email mahmoud@zalt.me
git config --global user.name 'Mahmoud Zalt'

# global get
git config --global --get user.email
git config --global --get user.name
```



1. **Check if an SSH key is already set up**:
   Run the following command to check if you have an existing SSH key:
   ```bash
   ls -al ~/.ssh
   ```
   Look for files like `id_rsa` and `id_rsa.pub`. If they exist, you already have an SSH key.

2. **Generate a new SSH key (if needed)**:
   If no SSH key exists, generate one using:
   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```
   Press Enter to accept the default file location and set a passphrase if desired.

3. **Add the SSH key to the SSH agent**:
   Start the SSH agent and add your key:
   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_rsa
   ```

4. **Add the SSH key to your GitLab account**:
   - Copy your public key to the clipboard:
     ```bash
     pbcopy < ~/.ssh/id_rsa.pub
     ```
   - Go to your GitLab account, navigate to **Settings > SSH Keys**, and paste the key.

5. **Test the SSH connection**:
   Verify that the SSH connection to GitLab works:
   ```bash
   ssh -T git@gitlab.com
   ```
   You should see a message like: `Welcome to GitLab, <username>!`

6. **Retry the clone command**:
   Run the clone command again:
   ```bash
   git clone git@gitlab.com:tigertrade/website.git
   ```

This should resolve the issue. Let me know if you encounter further problems!
