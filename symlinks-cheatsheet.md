# Symlinks Cheat Sheet

## What Is a Symlink?

A tiny file that stores a path string. Most commands follow it transparently — they see the target, not the link.

## Creating & Managing

| Command | What it does |
|---------|-------------|
| `ln -s target link_name` | Create a symlink (target first, link name second) |
| `ln -sf target link_name` | Overwrite an existing symlink |
| `ln target link_name` | Create a hard link |
| `rm link_name` | Remove a link (doesn't affect the target) |

## Inspecting

| Command | What it does |
|---------|-------------|
| `ls -l` | Shows `->` arrow and `l` prefix for symlinks |
| `ls -li` | Also shows inode numbers (useful for hard links) |
| `readlink link` | Shows the stored path (one step) |
| `readlink -f link` | Follows the full chain to the final target |
| `file link` | Shows what type of thing the link points to |
| `test -e link` | Follows the link — false if target is missing |
| `test -L link` | Checks the link itself — true even if dangling |

## Relative vs Absolute

| Type | Pros | Cons |
|------|------|------|
| **Relative** (`foo/file.txt`) | Portable — whole directory tree can move or be copied to another machine | Breaks if you move the symlink relative to its target |
| **Absolute** (`/home/user/foo/file.txt`) | Survives moving the symlink anywhere | Breaks if the target moves, or on a different machine |

**Key rule:** Relative paths resolve from where the **link lives**, not from where you ran `ln -s`.

## Symlinks vs Hard Links

| | Symlink (`ln -s`) | Hard link (`ln`) |
|---|---|---|
| What it stores | A path string | Same inode as the target |
| Works on directories | Yes | No |
| Survives target deletion | No (becomes dangling) | Yes (data persists until last name is removed) |
| Survives being moved | Absolute: yes. Relative: only if relative position is preserved | Always |
| Cross-filesystem | Yes | No |

## Dangling Symlinks

When a symlink's target is deleted, the link still exists but points to nothing. `ls` still shows it, but using it gives "No such file or directory".

## Common Real-World Patterns

- **Homebrew:** Symlinks in `/opt/homebrew/bin/` point into the Cellar. Upgrades just repoint the link.
- **App bundles:** Apps in `/Applications/` place symlinks in `/usr/local/bin/` so they're callable from the terminal.
- **Dotfiles:** Real configs live in a git repo, symlinks from `~` point into the repo.
- **Version switching:** A single symlink like `app -> app-v2/` allows atomic version switches by repointing.
