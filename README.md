README of test-gitflow
======================

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

### Initialization

To initialize a new repo with the basic branch structure, use:

사용할 레포의 master/main 이름등을 맞춰줘야 한다.

```
git flow init
```
