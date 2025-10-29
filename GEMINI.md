# GEMINI.md: Dotfiles Analysis

## Directory Overview

This directory, `dotfiles`, contains personal configuration files for the Zsh shell environment. It is managed as a Git repository, allowing for version control and synchronization of shell settings across different systems. The primary purpose is to customize the shell prompt, manage environment variables, and integrate various tools and plugins for an enhanced command-line experience.

## Key Files

*   **`zprofile`**: This file is sourced when a login shell is started. It is used to set environment variables that should be available to all processes. In this configuration, it:
    *   Initializes the Homebrew environment.
    *   Adds Sublime Text's command-line helper to the `PATH`.
    *   Adds user-specific binary directories (`~/bin`, `~/.local/bin`) to the `PATH`.
    *   Sets up environment variables (`GOROOT`, `GOPATH`, `PATH`) for the Go programming language.

*   **`zshrc`**: This is the main configuration file for interactive Zsh sessions. It is sourced every time a new terminal session is started. It handles the setup of the shell's appearance and functionality, including:
    *   Loading and configuring "Oh My Zsh," a framework for managing Zsh configuration.
    *   Setting the shell theme to "strug".
    *   Loading several Oh My Zsh plugins: `git`, `brew`, `macos`, `pod`, and `forklift`.
    *   Setting up command-line completions for Homebrew.
    *   Loading a custom bootstrap script for "fabric".
    *   Adding the LM Studio CLI to the `PATH`.

*   **`README.md`**: A minimal README file for the repository.

## Usage

These dotfiles are intended to be used by symlinking them from the user's home directory. For example, the `zshrc` file in this repository would be symlinked as `~/.zshrc`. This allows the user to maintain their shell configuration in a version-controlled repository while having the files in the correct location for the shell to read them.

**To set up this configuration:**

1.  Clone this repository to a location like `~/dotfiles`.
2.  Create symbolic links from the home directory to the files in this repository. For example:
    ```bash
    ln -s ~/dotfiles/zshrc ~/.zshrc
    ln -s ~/dotfiles/zprofile ~/.zprofile
    ```
3.  Start a new terminal session to see the changes.
