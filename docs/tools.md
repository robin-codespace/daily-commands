# Common Development Tools

Here are some command line tools I frequently use as a software engineer:

# AWS CLI
[Official AWS CLI Documentation](https://aws.amazon.com/cli/)

The AWS Command Line Interface (CLI) is a unified tool to manage your AWS services which contains a big pack of commands.


## aws sso login + .aws/credentials 
Authenticate with AWS using Single Sign-On (SSO) which I used very often when do local development to connect AWS environment. 

Examples:
- `aws sso login --profile dev` - Login to dev environment
- `aws sso login --profile prod` - Login to production environment


# direnv + .envrc file
[Official direnv Documentation](https://direnv.net/)

direnv is a tool that loads and unloads environment variables depending on the current directory. It's very useful for project-specific environment configurations.

## direnv allow
Approve loading environment variables from the current directory's .envrc file.
Example:
- `direnv allow` - Allow loading of environment variables defined in .envrc

## direnv deny
Revoke permission to load environment variables from .envrc file.
Example:
- `direnv deny` - Deny loading of environment variables from current .envrc

# just + Justfile
[Official just Documentation](https://just.systems/)

just is a handy command runner that helps you save and run project-specific commands. Commands are stored in a file called justfile or Justfile. It's like make but simpler and more intuitive.

Examples:
- `just build` - Run build command defined in justfile
- `just test` - Run test command defined in justfile
- `just deploy` - Run deploy command defined in justfile

# brew
[Official Homebrew Documentation](https://brew.sh/)

Homebrew is the most popular package manager for macOS. It helps you easily install, update and manage various software packages.

## Common Commands Examples:
- `brew install package_name` - Install a new package
- `brew uninstall package_name` - Remove an installed package
- `brew update` - Update Homebrew itself and package information
- `brew upgrade` - Upgrade all installed packages
- `brew list` - List all installed packages
- `brew cleanup` - Remove old versions of installed packages
