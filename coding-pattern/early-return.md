# Early Return

a.k.a. guard clause



non early return code:

```python
def foo():
    if bar != 0:
        result = a
    else:
        result = b
    return result
```



위의 코드를 Early Return으로 바꾸면:

```python
def foo():
    if a != 0:
        result = a
        return result
    
    result = b
    return result
```



### 중첩 조건문의 간소화

다음과 같이 중첩된 조건문이 있을 때:

```python
def foo():
  if a != 0:
    if a == 100:
      result = funcA1()
    else:
      result = funcA2()
  else:
    result = funcB()
  return result

```



위의 코드를 Early Return으로 바꾸면:

```python
def function foo():
  if a == 0:
    result = funcB()
    return result
  
  if a == 100:
    result = funcA1()
    return result
    
  result = funcA2()
  return result
```



Early Return을 사용할 경우, 어떤 구문이 어떠한 조건에서 실행되는지 명확하게 확인 가능하다.

또한 함수 하나가 하나의 기능만을 수행하게 만들기 때문에 Clean Code 원칙에도 부합한다.