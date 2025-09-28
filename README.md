# AgentConfigs
These are my personal Agent configurations.

I typically favor Claude Code, but use a variety of tools depending on the task.

# Tools that are used:
This command uses Homebrew, a popular package manager for macOS and Linux, to install several useful command-line tools in one step. Each tool serves a different purpose:

* **ast-grep:** A tool for searching code using abstract syntax trees, allowing for more precise and language-aware queries than simple text search.
* **fd:** A fast and user-friendly alternative to the traditional find command, used for searching files and directories.
* **ripgrep:** A line-oriented search tool that recursively searches your directory for a regex pattern, similar to grep but much faster.
* **fzf:** A general-purpose command-line fuzzy finder, which helps you quickly filter and select items from lists, files, or command history.
* **jq:** A lightweight and flexible command-line JSON processor, useful for parsing, filtering, and transforming JSON data.
* **yq:** Similar to jq, but for YAML files, allowing you to process and manipulate YAML data from the command line.

By running this command, you ensure that all these tools are installed and available for use in your terminal, streamlining tasks related to searching, filtering, and processing files and data.

```brew install ast-grep fd ripgrep fzf jq yq```
