# 제어문
## 반복문 (for, while)
시퀀스형 데이터를 순회할 때 사용된다.

### String 순회
```python
for char in 'ASDFASDF':
	print(char)

A
S
D
F
A
S
D
F
```

### 리스트 순회
```python
l = [1, 2, 3, 4, 5, 6, 'list01', 'list02']

for i in l:
	print(i)
	
1
2
3
4
5
6
list01
list02
```
i 는 순차적으로 리스트 내부에 있는 값을 할당받게 된다.

리스트 내부에 또다른 리스트가 있을 경우 그 값을 순차적으로 출력하려면 for 문을 중첩하여 사용하여 주면 된다.

```python
l = [
    [1,2,3],
    [4,5,6],
    [7,8,9],
]

for i in l:
    for e in i:
    	print(e)
    
1
2
3
4
5
6
7
8
9

```


### 딕셔너리 순회
```python
fruits = {
	'apple':'사과',
	'banana':'바나나',
	'cherry':'체리',
}

for item in fruits:
	print(item)

apple
banana
cherry
```
딕셔너리를 그냥 출력하게 되면 key 값만 나온다. 위의 결과는 아래의 결과와 같다.

```python
for item in fruits.keys():
	print(item)
	
apple
banana
cherry
```

values 들을 출력하고 싶을 때는 위의 `keys()` 부분을 `values()` 로 바꾸어 주면 된다.

for 문으로 key 값과 value 값을 전부 string 값을 출력하려면 아래와 같이 해보자

```python
for item in fruits.items():
    print(f'{item[0]}:{item[1]}')
```

### 딕셔너리 안의 딕셔너리 안의 리스트 순회
```python
# 해당하는 딕셔너리를 아래의 결과값과 같이 출력해보자.

# 변수 생성
girlgroups = {
     'girlsday':{
         'korean':'걸스데이',
         'members':'민아,혜리,유라,소진'.split(','),
     },
     'redvelvet':{
         'korean':'레드벨벳',
         'members':'아이린,슬기,웬디,조이,예리'.split(','),
    },
}

# 해당 변수의 값
{'girlsday': {'korean': '걸스데이', 'members': ['민아', '혜리', '유라', '소진']},
 'redvelvet': {'korean': '레드벨벳', 'members': ['아이린', '슬기', '웬디', '조이', '예리']}}

# 출력 결과
민아
혜리
유라
소진
아이린
슬기
웬디
조이
예리

# 내 나름대로의 정답.
for gir in girlgroups.values():
	for i in gir['members']:
   		print(i)
```

