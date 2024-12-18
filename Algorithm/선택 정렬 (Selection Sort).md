# 선택 정렬 (Selection Sort)

- 정렬 알고리즘 중 하나로, 가장 작은(혹은 큰) 값을 선택해 배열의 앞부분부터 채워 나가는 방식으로 작동

## 선택 정렬의 동작 방식
1. 배열 중에서 가장 작은 값 탐색
2. 해당 값을 배열의 가장 앞에 있는 값과 교환
3. 배열의 첫 번째 자리를 제외하고(이미 정렬된 부분), 남은 배열에서 위 과정을 반복
4. 배열 전체가 정렬될 때까지 반복

## 선택 정렬 구현 예시 (by Python)
```
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        # i 위치에서 가장 작은 요소 찾기
        min_idx = i
        for j in range(i + 1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        # 가장 작은 요소를 i 위치로 이동
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
```

## 선택 정렬의 동작 예시
    시작 배열: [64, 25, 12, 22, 11]

1. 전체 배열 중 가장 작은 값(11)을 찾아 첫 번째 위치(64)와 교환:
[11, 25, 12, 22, 64]

2. 나머지 배열 [25, 12, 22, 64]에서 가장 작은 값(12)을 두 번째 위치(25)와 교환:
[11, 12, 25, 22, 64]

3. 나머지 배열 [25, 22, 64]에서 가장 작은 값(22)을 세 번째 위치(25)와 교환:
[11, 12, 22, 25, 64]

4. 나머지 배열 [25, 64]에서 이미 정렬되어 있으므로 그대로 둠.

### 최종 배열: [11, 12, 22, 25, 64]