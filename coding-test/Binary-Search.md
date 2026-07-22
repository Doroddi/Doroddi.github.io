### 1. [easy] Search-Insert-Position (3:27) (O) [✓]
(https://leetcode.com/problems/search-insert-position/)

이진 탐색 알고리즘에 따라 타겟을 찾으면 해당 index를 반환, 찾지 못한다면 들어가야할 자리를 반환. Arrays.binarySearch()는 들어가야할 index를 (-( insertion point ) - 1)로 반환함.

### 2. [Medium] Find-First-And-Last-Position-Of-Element-In-Sorted-Array (20:58) (O) [✓]
(https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/)

Upper Bound와 Lower Bound를 찾는 문제. 기본 개념은 Upper Bound는 target보다 크거나 같은 수를 찾아가면서 처음으로 target보다 큰 수를 찾으면 그 index - 1이 중복된 target의 가장 오른쪽. Lower Bound는 작거나 같은수를 찾아가면 찾은 index가 target의 가장 왼쪽.  
이 때 해당 배열에 숫자가 없을 때 Upper Bound는 최종 (index - 1)과 target이 같은지 비교하면 되고, Upper Bound에 존재하지 않으면 당연히 Lower Bound를 찾을 때 없을 것이므로 중복 검사할 필요는 없음.  
더하여 배열의 길이가 0일 때와 1일 때 발생하는 배열 인덱스 정도 고려 정도?

### 3. [Easy] SqrtX (34:03) (O) [✓]
(https://leetcode.com/problems/sqrtx/)

기본 접근은 x의 제곱근의 정수 부분을 찾는 것이기 때문에 제곱했을 때 처음으로 x보다 커지는 수를 찾으면 됨. 이 말인즉슨 Upper Bound 찾는 것과 동일.  
문제 푸는데 시간이 오래 걸린 몇가지 이유는 첫 번째, 0과 1은 제곱했을 때 처음으로 커지는 수가 아닌 본인을 반환해야 하고, 두 번째, x의 범위가 int의 최댓값이기 때문에 제곱했을 때 int 최댓값 범위를 넘어서게 된다.  
이를 해결하기 위해서 떠올린 방법은 제곱하는 수를 형 변환하고 조건 검사도 형 변환 상태로 진행 후 출력은 int로 하기, 또는 int 최댓값의 제곱근 정수 부분까지로 탐색 범위 제한하기 두 가지 방법을 떠올렸는데 형 변환이 코드 작성이 훨씬 간단하여 그렇게 진행하였다. 한 가지 걸린 것은 형 변환 시 시간 효율이 떨어질 수 있지 않을까 했는데 애초에 O(logN)이라 크게 지장 없는 듯하다.  
+) 코드 분석 결과, 조금 더 최적화하면 long으로 형 변환하여 조건 검사, 다른 방식은 나눗셈으로 접근 등이 있네.

### 4. [Midium] Search-A-2D-Matrix (X/O) [✓]
(https://leetcode.com/problems/search-a-2d-matrix/)

못 푼 이유: 시간 초과  

레전드 뇌 녹음 이슈.  
조건에 따르면 정렬된 1차원 배열이나 다름이 없기 때문에 1차원 배열이라고 생각하고 binary search를 하면 되는데, **순수하게 1차원 배열의 인덱스 값을 2차원 배열의 row, column 값으로 바꾸는걸 잘못 계산함.**

### 5. [Easy] Count-Complete-Tree-Nodes (X)
(https://leetcode.com/problems/count-complete-tree-nodes/)

못 푼 이유: 시간 초과. 완전 이진 트리의 노드 개수 구하기. 어케 함?

### 6. [Medium] Search-In-Rotated-Sorted-Array-II (13:35) (O/?)
(https://leetcode.com/problems/search-in-rotated-sorted-array-ii/)

1. 정렬 후 binary search. 흠, 절대 이렇게 풀라고 준 문제는 아닌듯 싶죠?  

2. 처음 앞 수보다 뒷 수가 작아질 때를 기점으로 회전 시킨 후 binary search 하는 방식으로 해결하니 O(n)으로 줄었지만, 여전히 요구하는 정답은 아닌듯 함.

### 7. [Easy] First-Bad-Version (09:56) (O) [✓]
(https://leetcode.com/problems/first-bad-version/)

처음으로 불량이 나오는 버전을 찾는다. = 타겟보다 처음으로 큰 수를 찾는다. = Upper Bound + 1 찾기 = 타겟들 중 가장 작은 수를 찾는다. = Lower Bound 찾기. 모두 동일.

### 8. [Easy] Missing-Number (04:52) (O) 
(https://leetcode.com/problems/missing-number/)

0~n 중 n개가 들어있으므로 들어있지 않은 하나의 수를 찾기 위해 temp array를 만들어 해쉬 방식으로 하면 O(n)으로 해결 가능.
Follow-up이 요구한 공간 복잡도 O(1)을 만족하려면 오또케 해야할까? -> 배열 각 인덱스 값에 들어있는 수의 인덱스 칸을 찾아가서 스왑하는 방식으로 추가 메모리 없이 체크를 했는데, 메모리 효율이 떨어짐. 시간 효율은 떨어질 것 같은 느낌이였긴 했는데 메모리는 와이????

### 9. [Easy] Kth-Missing-Positive-Number (13:20) (O)
(https://leetcode.com/problems/kth-missing-positive-number/)

해쉬셋에 주어진 배열에 담긴 수를 담고 1부터 넣어보면서 해쉬셋에 없으면 카운팅 있으면 노 카운팅. 시간 복잡도 O(n)으로 생각되는데(확신 x) 그래서 시간, 공간 점수가 둘 다 낮은 것일까?  
느낌상은 binary search로 해결하여 O(logN)으로 해결할 수 있을 것 같은데? 
