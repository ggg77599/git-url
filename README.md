### git-url

#### Install

copy this file to your `$PATH`, then the git command will automatically find the command.

#### Usage

```shell
git url [remote/branch] [file]
```

#### Example
```shell
git url                        # https://github.com/ggg77599/git-url
git url origin                 # https://github.com/ggg77599/git-url
git url origin/main            # https://github.com/ggg77599/git-url/tree/main
git url README.md              # https://github.com/ggg77599/git-url/blob/main/README.md
git url origin README.md       # https://github.com/ggg77599/git-url/blob/main/README.md
git url origin/main README.md  # https://github.com/ggg77599/git-url/blob/main/README.md

git url gitlab                 # https://gitlab.com/ggg77599/git-url
git url gitlab/main            # https://gitlab.com/ggg77599/git-url/tree/main
git url gitlab README.md       # https://gitlab.com/ggg77599/git-url/blob/main/README.md
git url gitlab/main README.md  # https://gitlab.com/ggg77599/git-url/blob/main/README.md
```

#### Special rules

if you have your self-host gitlab or other git repository, you can modify `this_is_my_own_special.rule` part to fit your use case.

#### Credit

This project is inspired by https://github.com/maorfr/git-url
