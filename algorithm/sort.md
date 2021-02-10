# 정렬

<br>

## 버블 정렬(Bubble Sort)

> 인접한 두 개의 원소를 비교하며 자리를 계속 교환하는 방식

<br>

정렬 과정

- 첫 번째 원소부터 인접한 원소끼리 계속 자리를 교환하면서 맨 마지막 자리까지 이동한다.
- 한 단계가 끝나면 가장 큰 원소가 마지막 자리로 정렬된다.

<br>

시간복잡도

- O(n^2)

<br>

코드구현

```python
def BubbleSort(array) : # array: 정렬할 List
    for i in range(len(array)-1,0,-1): # 탐색할 범위의 끝
        for j in range(0,i):
            if a[j] > a[j+1]: # 뒤에 있는 값보다 크면
                a[j], a[j+1] = a[j+1], a[j] # 값을 바꿔준다.
```



