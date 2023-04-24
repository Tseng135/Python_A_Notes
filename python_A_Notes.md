## * Using list expression to define a string variable
```python
q2_list = [1, 2, 6, 10, 19, 21]
output2 = ''.join([f'The square of {num} is {num\*\*2}!\n' for num in q2_list]).strip()
print(output2)  
```
output:  
The square of 1 is 1!  
The square of 2 is 4!  
The square of 6 is 36!  
The square of 10 is 100!  
The square of 19 is 361!  
The square of 21 is 441!  

## * Nested string 

```python
output7 = '\n'.join(' '.join(str(j+1) for j in range(i+1)) for i in range(5))
```

output:

'1\n1 2\n1 2 3\n1 2 3 4\n1 2 3 4 5'


1  
1 2	  
1 2 3  
1 2 3 4  
1 2 3 4 5

## * Judging whether a varible is iterable



```python
from _collections_abc import Iterable:
isinstance(object, Iterable)

'''module: collection_abc	Class: Iterable'''
```


## * Using generator function to construct Fibonacci array

```python
def gen_fib(max_value):
    a, b = 0, 1
    while a < max_value:
        yield a
        a, b = b, a + b

print([num for num in gen_fib(100)])
```

## * Dictionary concatenation, expression and unpacking
```python
q13_1 = {1:10, 2:20, 3:30}
q13_2 = {4:40, 5:50}
q13_3 = {6:60, 7:70, 8:80}
q13_4 = {9:90}
output13 = {**q13_1, **q13_2, **q13_3, **q13_4}
print(output13)

output13 = {key: value for dic in [q13_1, q13_2, q13_3, q13_4] for key, value in dic.items()}
print(output13)
```

## * dic.get() method
```python
q18_d1 = {'x': 120, 'y': 200, 'z':300, 'w': 30}
q18_d2 = {'x': 90, 'y': 120, 'z':300, 'm': 120}
output = {}
for key in q18_d1.keys():
    output[key] = q18_d1[key] + q18_d2.get(key, 0)
#.get方法 可以获得指定键的值，0是默认返回值
```

## * Constructing nested dictionary
**method 1 :dictionary reference**


```python
q20_list = ['John', 'Danise', 'David', 'Kelly']
output = {}
nested_dic = output
for element in q20_list:
    nested_dic[element] = {}
    nested_dic = nested_dic[element]
print(output)
```
output:{'John': {'Danise': {'David': {'Kelly': {}}}}}

**methond 2 : recursive function**

```python
q20_list = ['John', 'Danise', 'David', 'Kelly']
def nested_function(given_list):
    if len(given_list) == 1:
        return {given_list[0]:{}}
    return {given_list[0]:nested_function(given_list[1:])}
print(nested_function(q20_list))
```
output:{'John': {'Danise': {'David': {'Kelly': {}}}}}

## * Using .zip() method combine more iterables

```python
keys = ['##', '$$', '!!', '**', '))', '((']
values = [11, 44, 66, 99, 11, 0]

output = {key:value for key, value in zip(keys, values)}
'''
zip()的返回值是将iterables 里的元素存储到元组里
'''
print(output)
```

output：
{'##': 11, '$$': 44, '!!': 66, '**': 99, '))': 11, '((': 0}``	`]K