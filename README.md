[user]
    name = Your Name
    email = your.email@example.com
    signingkey = your_gpg_key_id  # If you use GPG for commit signing

[core]
    editor = code --wait  # Set VSCode as the default editor, adjust to your preferred editor
    excludesfile = ~/.gitignore_global
    autocrlf = input  # Useful for handling line endings between different OSes
    pager = less -FRX  # Improve the default pager behavior

[color]
    ui = auto  # Enable colored output for Git

[color "branch"]
    current = yellow reverse
    local = yellow
    remote = green

[color "diff"]
    meta = yellow bold
    frag = magenta bold
    old = red bold
    new = green bold

[color "status"]
    added = green
    changed = yellow
    untracked = red bold

[alias]
    # Shortcuts for common commands
    st = status
    co = checkout
    br = branch
    ci = commit
    df = diff
    lg = log --oneline --graph --decorate --all

    # Better log formatting
    l = log --pretty=format:'%C(yellow)%h%C(reset) - %C(bold blue)%an%C(reset), %C(dim green)%ar%C(reset) : %C(white)%s%C(reset)'

    # Enhanced diff
    d = diff --word-diff=color

    # Graphical log
    g = log --graph --all --decorate --oneline --simplify-by-decoration

    # Save and apply stashes
    save = stash save
    pop = stash pop

    # Interact with GitHub/GitLab
    pr = "!hub pull-request"  # Requires hub tool
    gl = "!glab mr create"  # Requires glab tool

    # Quick commit with message
    cm = commit -m

    # Amend the previous commit
    amend = commit --amend --no-edit

    # Show the history of a file
    hist = log --follow --date=short --pretty=format:'%C(yellow)%h%C(reset) %C(cyan)%ad%C(reset) %C(dim green)%an%C(reset) %C(white)%s%C(reset)'

    # List all branches sorted by the most recent commit
    brs = branch --sort=-committerdate

    # Rebase on the current branch
    rb = rebase -i

[push]
    default = simple  # Use simple push behavior

[fetch]
    prune = true  # Prune remote-tracking branches no longer on the remote

[merge]
    ff = false  # Never fast-forward merges

[rebase]
    autosquash = true  # Automatically squash fixup and squash commits during rebase

[filter "lfs"]
    clean = git-lfs clean -- %f
    smudge = git-lfs smudge -- %f
    required = true

[pull]
    rebase = false  # Merge pulls by default

[http]
    sslVerify = true  # Ensure SSL verification for secure connections
    postBuffer = 157286400  # Increase the buffer size for large pushes

[credential]
    helper = cache --timeout=3600  # Cache credentials for an hour
    # Use the following line if you prefer storing credentials in memory
    # helper = store

