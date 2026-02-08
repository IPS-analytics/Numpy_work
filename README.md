# Numpy homework
```python
import numpy as np

def my_array(N: int) -> np.array:
    arr = np.arange(N-1, -1, -1)    
    return arr
print(my_array(30))
```
Result: 

[29 28 27 26 25 24 23 22 21 20 19 18 17 16 15 14 13 12 11 10  9  8  7  6
  5  4  3  2  1  0]
  ```python
import numpy as np
 
def sum_matrix(N: int) -> int:
    arr = np.arange(N,-1,-1)
    print("Массив arr:", arr)
    my_matrix = np.diag(arr)
    print("Диагональная матрица my_matrix:\n", my_matrix)
    return np.sum(my_matrix)
sum_matrix(8)
```
Result: 

Массив arr: [8 7 6 5 4 3 2 1 0]

Диагональная матрица my_matrix:

 [[8 0 0 0 0 0 0 0 0]
 
 [0 7 0 0 0 0 0 0 0]
 
 [0 0 6 0 0 0 0 0 0]
 
 [0 0 0 5 0 0 0 0 0]
 
 [0 0 0 0 4 0 0 0 0]
 
 [0 0 0 0 0 3 0 0 0]
 
 [0 0 0 0 0 0 2 0 0]
 
 [0 0 0 0 0 0 0 1 0]
 
 [0 0 0 0 0 0 0 0 0]]

np.int64(36)
```python
import numpy as np
users_stats = np.array(
    [
        [2, 1, 0, 0, 0, 0],
        [1, 1, 2, 1, 0, 0],
        [2, 0, 1, 0, 0, 0],
        [1, 1, 2, 1, 0, 1],
        [0, 0, 1, 2, 0, 0],
        [0, 0, 0, 0, 0, 5],
        [1, 0, 0, 0, 0, 0],
        [0, 1, 1, 0, 0, 0],
        [0, 0, 0, 1, 1, 3],
        [1, 0, 0, 2, 1, 4]
    ], np.int32
)

next_user_stats = np.array([0, 1, 2, 0, 0, 0])

import numpy as np

def cosine(users_stats, next_user_stats):
    similarities = []
    for u in users_stats:
        sim = np.dot(next_user_stats, u) / (np.linalg.norm(next_user_stats) * np.linalg.norm(u))
        similarities.append(sim)
    return int(np.argmax(similarities))  
result = cosine(users_stats, next_user_stats)
print("Индекс самого похожего пользователя:", result)
```
Result: 
Индекс самого похожего пользователя: 7
