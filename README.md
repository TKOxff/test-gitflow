test-gitflow
============

git-flow 라이브러리 사용 테스트

## 1. Create Git Repo on Github

사전 준비 작업

### Adding a local repository to GitHub using Git

1. Create a new repository on GitHub.com. 

To avoid errors, do not initialize the new repository with README, license, or gitignore files. 

2. on GitHub.com's Quick Setup page, click  to copy the remote repository URL.

3. Open Terminal.

4. Change the current working directory to your local project.

create a new repository on the command line

```zsh
git init

git add README.md
git commit -m "first commit"

# 마스터 브랜치 이름을 main으로 명명
git branch -M main
```

5. Add the URL for the remote repository where your local repository will be pushed.

push an existing repository from the command line

```zsh
$ git remote add origin <REMOTE_URL>
# Sets the new remote
$ git remote -v
# Verifies the new remote URL
```

6. Push the changes in your local repository to GitHub.com.

```zsh
$ git push -u origin main
# Pushes the changes in your local repository up to the remote repository you specified as the origin
```

**The source**

https://docs.github.com/en/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github?platform=mac#adding-a-local-repository-to-github-using-git


## 2. git-flow

https://github.com/nvie/gitflow

### Initialization

To initialize a new repo with the basic branch structure, use:

사용할 레포의 master/main 이름등을 맞춰줘야 한다.

```zsh
  git flow init
```

### Creating feature branches

To start feature branches, use:

```zsh
git flow feature start <name> [<base>]

# Without the git-flow
git checkout develop
git checkout -b feature_branch
```

### Finishing a feature branch

When you’re done with the development work on the feature, the next step is to merge the feature_branch into develop.

> 이 명령은 로컬 브랜치를 머지하고 리모트에는 반영되지 않는다. 그리고 PR을 만들 수 없게된다?

```zsh
git flow feature finish feature_branch

# Without the git-flow
git checkout develop
git merge feature_branch
```

### Create a pull request

When done, open a `pull request` to your feature branch.

> 리모드에 PR을 생성한다.
> 회사등 공동 작업이라면 feature finish하기 전에 PR부터 만들어야 한다.

```zsh
  git flow feature publish <name>
```

To push/pull a feature branch to the remote repository, use:

```zsh
    git flow feature pull <remote> <name>
```
