---
layout: post
title: Python replace() 사용방법 및 예제
subtitle: 문자열 치환 함수
categories: python
tags: [python]
---

## replace 함수

특별한 라이브러리를 import 하지 않고 사용할 수 있는 파이썬 내장 함수로 특정 문자를 새로운 문자로 변경하는 기능을 가지고 있습니다.

> #### str.replace(old, new, [count])
>
> - str : 문자열
> - old : 문자열에서 찾을 문자
> - new : 변경하고 싶은 문자
> - count : 왼쪽부터 치환하고 싶은 횟수

<br>

## replace 함수 사용 예시

### 문자 변경

```python
str = 'hello world'
str.replace('hello', 'hi')
```

```bash
hi world
```

### 횟수 지정하여 문자 변경

```python
str = 'abcabcababab'
str.replace('ab', '-', 2)
```

```bash
-c-cababab
```

`abcabcababab`에서 왼쪽부터 2개의 `ab`만 치환
