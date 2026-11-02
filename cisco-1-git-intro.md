# My First Git Lab
This is my first document stored in Git.

## Things I Learned
- Git tracks changes to files.
- GitHub stores my repository online.
- **SSH keys** keep my account secure.

<hr>

## Configuring User using GitBash
- git config --global user.name "Benjamin Pedrin"
- git config --global user.email "pedrinb@students.westerntc.edu"
- git config --global core.autocrlf true
- git config --global --list

## Creating SSH keys
- ssh-keygen -t ed25519 -C "pedrinb@students.westerntc.edu"

### Start the agent and add the key (Holds key in memory while computer is on)
- eval "$(ssh-agent -s)"
- ssh-add ~/.ssh/id_ed25519

### Print & Copy Public Key
- cat ~/.ssh/id_ed25519.pub

### Testing your connection
- ssh -T git@github.com

<hr>