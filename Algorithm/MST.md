# MST(Minimum Spanning Tree)

> 가중치 그래프에서 모든 정점들을 연결하는 간선들의 가중치의 합이 최소가 되는 트리를 찾는 문제

<br>

## 프림 알고리즘

> 한 정점에 연결된 간선들 중 하나씩 선택하면서 최소 신장 트리를 만들어 가는 방식(정점 중심)

<br>

### &#9997; 진행방법

1. 임의의 정점을 하나 선택해서 시작
2. 선택한 정점들과 인접하는 정점들 중에 최소 비용의 간선이 존재하는 정점 선택
3. 모든 정점이 선택될 때 까지 두 번째 과정 반복

<br>

### &#128240; 코드 구현

```python
def MST_PRIM(G,s):                       # G: 그래프, s: 시작 정점
    key = [INF] * N                      # 가중치를 무한대로 초기화
    pi = [0] * N          				 # 정점이 트리에 연결될 때 사용할 간선 정보 초기화
    visited = [False] * N                # 방문 여부 초기화
    key[s] = 0                           # 시작 정점의 가중치를 0으로 설정
    
    for _ in range(N):                   # 정점의 개수만큼 반복
        minIndex = -1
        min = INF
        for i in range(N):               # 방문 안한 정점중 최소 가중치 정점 찾기
            if not visited[i] and key[i] < min:
                min = key[i]
                minIndex = i
        visited[minIndex] = True         # 최소 가중치 정점 방문처리
        for v, val in G[minIndex]:       # 선택 정점의 인접한 정점 중
            if not visited[v] and val < key[v]:
                key[v] = val             # 가중치 갱신
                pi[v] = minIndex         # 트리에서 연결될 부모 정점
```

<br>

## 크루스칼 알고리즘

> 사이클이 생기지 않는 최소 가중치 간선을 하나씩 선택해서 최소 신장 트리를 찾는 알고리즘(간선 중심)



### &#9997; 진행방법

1. 모든 간선을 가중치에 따라 오름차순으로 정렬
2. 가중치가 가장 낮은 간선부터 선택하면서 트리를 증가시킨다.
3. 사이클이 존재하면 다음으로 가중치가 낮은 간선 선택
4. n-1개의 간선이 선택될 때까지 두 번째 과정을 반복



### &#128240; 코드 구현

```python
def MST_KRUSKAL(G):
    mst = []
    for i in range(N):
        Make_Set(i)
    G.sort(key = lambda t:t[2])                  # 간선의 가중치를 기준으로 정렬
    
    mst_cost = 0                                 # 선택한 간선들의 가중치 합
    
    i = 0
    while len(mst) < N-1:                        # 모든 정점을 연결하기 위해 필요한 최소한의 간선수를 충족할 때까지
        u,v,val = G[i]
        if Find_Set(u) != Find_Set(v):           # 탐색하는 간선의 두 정점이 다른 집합일 경우(연결 X)
            Union(u,v)                           # 각 정점이 속한 집합을 합해주고
            mst.append((u,v))                    # 간선 정보를 추가
            mst_cost += val                      # 간선의 가중치를 합에 추가
        i += 1
    return mst_cost
```

