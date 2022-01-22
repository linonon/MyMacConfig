# SSH Setting

1. Create ssh-key
    - `ssh-keygen -t rsa -C "linonon"

2. Run ssh-agent
    - (If not MacOS) eval "$(ssh-agent -s)"

3. Agent add ssh-key (If got "Permission denied")
    - `ssh-add` or `ssh-add ~/.ssh/id_rsa"`

4. Git setting ssh-key
    - Go to `github`'s `setting` -> `SSH and GPG keys`

5. Copy ssh-key to clipboard, then paste
    - `pbcopy < ~/.ssh/id_rsa_pub`
    - paste to `SSH and GPG keys`
