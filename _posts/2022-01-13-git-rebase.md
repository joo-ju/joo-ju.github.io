---
layout: post
title: Git rebase 사용하기
subtitle: 브랜치 최신화 | 여러 커밋 한개로 합치기
categories: Github
tags: [rebase]
---

## rebase 란?

## rebase로 브랜치 최신화 하기

git으로 협업하면서 기준이 되는 브랜치(예를 들면 master)는 계속 작업을 진행하기 때문에 내가 작업하는 브랜치에는 최근 변경사항이 반영되어 있지 않기 때문에 최신화가 필요

### 1. base가 되는 브랜치 최신화

master 브랜치를 가장 최신 상태로 변경한다.

```bash
git checkout master
git pull origin master
```

### 2. 내가 작업하는 브랜치 최신화

```bash
git checkout dev
git rebase master
```

## rebase로 여러 커밋 하나로 합치기

### 1. rebase 사용

최신 커밋부터 총 3개를 합치고 싶으면 HEAD~3라고 입력한다. (2개라면 2라고 하면 된다.)

```bash
git rebase -i HEAD~3
```

<br>

### 2. 합칠 커밋 선택

어떤 커밋으로 합칠 것인지 선택한다.
![image](https://user-images.githubusercontent.com/96608232/149260216-0c455812-1039-48f0-9238-0b97afba62df.png)

최상단의 커밋을 제외하고 모두 pick을 s(squash)로 변경한 후 `:wq`를 입력해 저장&종료를 한다.
(squash인 커밋들을 pick으로 합치겠다는 의미)
![image](https://user-images.githubusercontent.com/96608232/149286742-b0b79689-42ad-4f7a-9a28-b5770a82aa75.png)

<br>

### 3. 커밋 메세지 수정

아래와 같은 커밋을 편집할 수 있는 화면이 나오면 남겨 놓을 1개의 커밋만 빼고 모두 삭제해준다.

![image](https://user-images.githubusercontent.com/96608232/149288386-cd8a576d-0721-48de-968c-cc7fe2eca72f.png)

모두 삭제했으면 `:wq`를 입력해 저장&종료한다.
![image](https://user-images.githubusercontent.com/96608232/149288628-aad3e28a-cc44-4a6b-8a17-088f78349415.png)

<br>

### 4. push 하기

강제 push를 해준다.

```bash
git push -f origin dev
```
