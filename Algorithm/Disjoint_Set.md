# Disjoint set(상호배타적 집합)

> 서로 중복 포함된 원소가 없는 집합들로 교집합이 없음. 집합에 속한 하나의 특정 원소(대표자)를 통해 각 집합들을 구분

<br>

## 상호배타 집합 연산

- Make-Set(x) : 원소 x만으로 구성된 집합을 생성하는 연산
- Finde-Set(x) : 임의의 원소 x가 속한 집합을 알아내기 위해 사용 -> 집합의 대표자를 확인
- Union(x,y) : x원소가 속한 집합과 y원소가 속한 집합을 하나의 집합으로 합치는 연산

<br>

## &#128240; 코드 구현

```python
# p[x]: 노드 x의 부모 저장
# rank[x]: 루트 노드가 x인 트리의 랭크 값 저장
def Make_set(x):
    p[x] = x
    rank[x] = 0

def Find_Set(x):
    if x != p[x]:                   # x가 루트가 아닌 경우
        p[x] = Find_set(p[x])       # Path Compression
    return p[x]

def Link(x,y):
    if rank[x] > rank[y]:
        p[y] = x
    else:
        p[x] = y
    if rank[x] == rank[y]:
        rank[y] += 1

def Union(x,y):
    Link(Find_Set(x),Find_set(y))   
```



