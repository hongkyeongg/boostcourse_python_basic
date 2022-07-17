## 함수의 선언 문법
parameter : 함수의 입력 값 인터페이스<br>
argument: 실제 Parameter에 대입된 <br>
```
def 함수 이름 (parmaeter #1,…,):<br>
  수행문 #1(statements)<br>
  수행문 #2(statements)<br>
return <반환값><br>
```
## print formatting
### (1) % string (2) format 함수(3) fstring

```py
value=[1.1,2,3]
print(1,2,3)
print("a" + " " + "b" + " " + "c")
print("%d %d %d" % (1,2,3))
print("{} {} {}".format("a","b","c"))
print(f"value is {value}")

#일반적으로%-format 과str.format() 함수를사용함
print('%s %s' % ('one', 'two'))
print('{} {}'.format('one', 'two'))
print('%d %d' % (1, 2))
print('{} {}'.format(1, 2))

print("I eat %d apples." % 3)
print("I eat %s apples." % "five")
number = 3; day="three"
print("I ate %d apples. I was sick for %s days."% (number, day))
print("Product: %s, Price per unit: %f." % ("Apple", 5.243))

```

```py
age = 36; name='Sungchul Choi'
print("I’m {0} years old.".format(age))
print("My name is {0} and {1} years old.".format(name,age))
print("Product: {0}, Price per unit: {1:.3f}.".format("Apple", 5.243))

```

```py
#여유공간을지정하여글자배열+ 소수점자릿수를맞추기
print("Product: %5s, Price per unit: %.5f." % ("Apple", 5.243))
print("Product: {0:5s}, Price per unit: {1:.5f}.".format("Apple", 5.243))
print("Product: %10s, Price per unit: %10.3f." % ("Apple", 5.243))
print("Product: {0:>10s}, Price per unit: {1:10.3f}.".format("Apple", 5.243))
```

```py
# python 3.6 이후, PEP498에근거한formatting 기법
name = "Sungchul"
age = 39
print(f"Hello, {name}. You are {age}.")
print(f'{name:20}')
print(f'{name:>20}')
print(f'{name:*<20}')
print(f'{name:*>20}')
print(f'{name:*^20}')
number = 3.141592653589793
print(f'{number:.2f}')
```

## 삼항 연산자(Ternary operators)
```py
value = 12
is_even = True if value % 2 == 0 else False
print(is_even)
```

## function type hints
1. 사용자에게 인터페이스를 명확히 알려줄 수 있다.
2. 함수의 문서화시 parameter에 대한 정보를 명확히 알 수 있다.
3. mypy 또는 IDE, linter 등을 통해 코드의 발생 가능한 오류를 사전에 확인
4. 시스템 전체적인 안정성을 확보할 수 있다.
```py
def type_hint_example(name: str) -> str:
    return f"Hello, {name}"
```
## function docstring
- 파이썬 함수에 대한 상세스펙을 사전에 작성 -> 함수 사용자의 이행도 UP
- 세개의 따옴표로 docstring 영역 표시(함수명 아래)

## 파이썬 기본 데이터 구조
### - 스택과 큐(stack & queue with list)
### - 튜플과 집합(tuple & set) 
### - 사전(dictionary)
### - Collection 모듈

## stack 

### - 나중에 넣은 데이터를 먼저 반환하도록 설계된 메모리 구조
### - Last In First Out (LIFO)
### - Data의 입력을 Push, 출력을 Pop이라고 함
### - 리스트를 사용하여 스택 구조를 구현 가능
### - push를 append(), pop을 pop()를 사용

## 큐 (Queue)
### - 먼저 넣은 데이터를 먼저 반환하도록 설계된 메모리 구조
### - First In First Out (FIFO)
### - Stack과 반대되는 개념
### -파이썬은 리스트를 사용하여 큐 구조를 활용
### -put를 append(), get을 pop(0)를 사용

## deque
### -Stack과 Queue 를 지원하는 모듈
### - List에 비해 효율적인=빠른 자료 저장 방식을 지원함
### - rotate, reverse등 Linked List의 특성을 지원함
### - 기존 list 형태의 함수를 모두 지원함
### - rotate, reverse등 Linked List의 특성을 지원함
### - 기존 list 형태의 함수를 모두 지원함
### - deque 는 기존 list보다 효율적인 자료구조를 제공
### - 효율적 메모리 구조로 처리 속도 향상

```py
from collections import deque
deque_list = deque()
for i in range(5):
    deque_list.append(i)
    print(deque_list)
    deque_list.appendleft(10)
    print(deque_list)
```

```py
deque_list.rotate(2)
print(deque_list)
deque_list.rotate(2)
print(deque_list)
print(deque(reversed(deque_list)))
deque_list.extend([5, 6, 7])
print(deque_list)
deque_list.extendleft([5, 6, 7])
print(deque_list)
```

## defaultdict
## Dict type의 값에 기본 값을 지정, 신규값 생성시 사용하는 방법
```py
from collections import defaultdict
d = defaultdict(object) # Default dictionary를 생성
d = defaultdict(lambda: 0) # Default 값을 0으로 설정합
print(d["first"])
```
## Pythonic code
### - split & join
### - list comprehension
### - enumerate & zip
### - lambda & map & reduce
### - generator 
### - asterisk

### join
String으로 구성된 list를 합쳐 하나의 string으로 반환
```py
a=['appled','banna','tomato']

join_a=''.join(a)
join_a
```
```py
b=['appled','banana','test']
```
 ## list comprehension

### -기존 List 사용하여 간단히 다른 List를 만드는 기법
### - 포괄적인 List, 포함되는 리스트라는 의미로 사용됨
### - 파이썬에서 가장 많이 사용되는 기법 중 하나
### - 일반적으로 for + append 보다 속도가 빠름
```py
result=[i for i in range(10)]
result
```

```py
result1=[i for i in range(10) if i%2==0]
result1
```
```py
result4=[i for i in range(10) if i%3==0]
result4
```

```py
first='HELLO'
second='WORLD'

test=[i+j for i in first for j in second]
test
```
```py
a=['a','b','c']
b=['f','z','a']

test1=[i+j if i!=j  else i for i in a for j in b]
test1
#print(len(test1))
```

```py
setence='The quick brown fox jumps over the lazy dog'.split()


[[i.lower(),i.upper(),len(i)] for i in setence]
```

```py
setences='the quick brown Fox jumps The lazy dogs'.split()

[[setence.lower(),setence.upper(),len(setence)] for setence in setences]
```

```py
[[(j,i) for i in range(5)] for j in range(6,10)]
```
### enumerate
```py
test='hello my name IS HONG KYEONG hello hi'

text=list(set(test.split()))
```

```py
{v : i for i,v in enumerate(text)}
```

```py
kor=[30,40,50]
eng=[30,40,50]
math=[30,40,50]

[(i,v) for i,v in enumerate(zip(kor,eng,math))]
```
### lambda
```py
sum_function=lambda x ,y : x+ y
sum_function(10,20)
```
```py
(lambda x,y : x+y)(10,20)
```

```py
(lambda x : '-'.join(x.split(' ')))('hong kyoeng')
```
```py
test=(lambda x : x **2)
for i in range(10):
    print(test(i))
```

```py
ex=[1,2,3,4,5]
list_x=(lambda x : x **2)
list(map(list_x,ex))
```
```py
from functools import reduce
reduce(lambda x,y : x+y ,[1,2,3,4,5])
```

```py
def generate_list(value):
    result=[]
    for i in range(value):
        result.append(i)
    print(result)
generate_list(50)
```
```py
import sys
sys.getsizeof(result)
```
## genrate
### -iterable object를 특수한 형태로 사용해주는 함수
### - element가 사용되는 시점에 값을 메모리에 반환
#### : yield를 사용해 한번에 하나의 element만 반환함

```py
def generate_list(value):
    result=[]
    for i in range(value):
        yield i
generate_list(50)     
```
## Keyword arguments
### 함수에 입력되는 parameter의 변수명을 사용, arguments를 넘김

```py
def keyword_argument(name_keyword,age_argument):
    print('{0} \t {1} hell'.format(name_keyword,age_argument))
```
```py
keyword_argument('hello','5')
# print(keyword_argument(age_argument=6,name_keyword='hi'))
```
```py
def valiable_lenth(a,b,*args):
    print(args)
    print(a+b+sum(args))
    
valiable_lenth(1,2,3,4,5)
```

```py
#parameter의 기본 값을 사용, 입력하지 않을 경우 기본값 출력
def valiable_lenths(a,b=20,*args,**kwargs):
    print(a)
    print(b)
    print(type(args),args)
    print(type(kwargs),kwargs)

valiable_lenths(10,40,50,60,one=1,two=2,thrid='3')
```

## asterisk
### - 흔히 알고 있는 * 를 의미함
### - 단순 곱셈, 제곱연산, 가변 인자 활용 등 다양하게 사용
## asterisk – unpacking a container
### - tuple, dict 등 자료형에 들어가 있는 값을 unpacking
### - 함수의 입력값, zip 등에 유용하게 사용가능
```py
data=([1,2],[3,4],[5,6])
print(*data)
```
```py
data=([1,2],[3,4],[5,6],[7,8])
def test(x):
    for i in zip(*x):
        print(i)
test(data)
```






