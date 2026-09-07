### git-url

#### Install

copy this file to your `$PATH`, then the git command will automatically find the command.

#### Usage

```shell
git url [-n lineNumber] [-s] [[remote[/branch]] [file]]
```

##### Options

- `-n`: line number. Can specify once for single line (`#L10`) or twice for range (`#L10-L20`)
- `-s`: static link, uses tag (if exists at HEAD) or commit hash instead of branch name
- `-h`: show help message

#### Example
```shell
git url                        # https://github.com/ggg77599/git-url
git url origin                 # https://github.com/ggg77599/git-url
git url origin/main            # https://github.com/ggg77599/git-url/tree/main
git url README.md              # https://github.com/ggg77599/git-url/blob/main/README.md
git url origin README.md       # https://github.com/ggg77599/git-url/blob/main/README.md
git url origin/main README.md  # https://github.com/ggg77599/git-url/blob/main/README.md

# with line number options
git url -n 10 README.md              # https://github.com/ggg77599/git-url/blob/main/README.md#L10
git url -n 10 -n 20 README.md        # https://github.com/ggg77599/git-url/blob/main/README.md#L10-L20

# with static option
git url -s README.md                 # https://github.com/ggg77599/git-url/blob/9cf43d40f57181c3730e584b28f7762af0542d62/README.md

git url gitlab                 # https://gitlab.com/ggg77599/git-url
git url gitlab/main            # https://gitlab.com/ggg77599/git-url/tree/main
git url gitlab README.md       # https://gitlab.com/ggg77599/git-url/blob/main/README.md
git url gitlab/main README.md  # https://gitlab.com/ggg77599/git-url/blob/main/README.md
```

#### Special rules

if you have a self-hosted gitlab or other git repository on a non-standard SSH port, set `GIT_URL_SPECIAL_RULES` to map it to its HTTPS port:

```shell
export GIT_URL_SPECIAL_RULES="my.gitlab.host:10022:10443"
# multiple rules, separated by ;
export GIT_URL_SPECIAL_RULES="host1:10022:10443;host2:2222:443"
```

each rule is `host:sshPort:httpsPort`. leave `GIT_URL_SPECIAL_RULES` unset if you don't need this.

ssh hosts defined in your `~/.ssh/config` will be automatically resolved to their real hostnames.

#### Credit

This project is inspired by https://github.com/maorfr/git-url
