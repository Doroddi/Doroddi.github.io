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

### 8. [Easy] Missing-Number (04:52) (O/?) 
(https://leetcode.com/problems/missing-number/)

0~n 중 n개가 들어있으므로 들어있지 않은 하나의 수를 찾기 위해 t 인emp array를 만들어 해쉬 방식으로 하면 O(n)으로 해결 가능.
Follow-up이 요구한 공간 복잡도 O(1)을 만족하려면 오또케 해야할까? -> 배열 각덱스 값에 들어있는 수의 인덱스 칸을 찾아가서 스왑하는 방식으로 추가 메모리 없이 체크를 했는데, 메모리 효율이 떨어짐. 시간 효율은 떨어질 것 같은 느낌이였긴 했는데 메모리는 와이????

### 9. [Easy] Kth-Missing-Positive-Number (13:20) (O/?)
(https://leetcode.com/problems/kth-missing-positive-number/)

해쉬셋에 주어진 배열에 담긴 수를 담고 1부터 넣어보면서 해쉬셋에 없으면 카운팅 있으면 노 카운팅. 시간 복잡도 O(n)으로 생각되는데(확신 x) 그래서 시간, 공간 점수가 둘 다 낮은 것일까?  
느낌상은 binary search로 해결하여 O(logN)으로 해결할 수 있을 것 같은데? 

### 10. [Easy] Binary-Search (02:15) (O) [✓]
(https://leetcode.com/problems/binary-search/)

### 11. [Medium] Find-Peak-Element (X/O)
(https://leetcode.com/problems/find-peak-element/)

못 푼 이유: 시간 초과.
접근은 배열을 두 구간으로 나눠 반반 씩 분할하여 peak element인지 검사한다는 생각으로 분할 정복 알고리즘으로 재귀 함수를 구현하였다. 배열 인덱스 부분을 해결하지 못하여 해결하지 못했음.  
결국 인덱스 문제 해결했지만 큰 에러 포인트는 코드를 짤 때 이러한 인덱스 문제를 어떻게 깔끔하게 해결하면서 갈 지에 대한 고민을 해봐야 함. 기본 알고리즘을 짜도 인덱스 등의 세부 조건 등을 정답 제출 후 발견하여 코드에 계속해서 추가하는 방식으로 코드를 짜다 보니 알고리즘의 정확성과 가독성을 매우매우 저해함.

### 12. [Easy] Intersection-Of-Two-Arrays (11:53) (O/?)
(https://leetcode.com/problems/intersection-of-two-arrays/)

binary search가 주제니까 각 배열 정렬 후 더 짧은 배열에 있는 각 원소를 더 긴 배열에서 binary search해서 존재하면 intersection 셋에 저장.  
이전에 풀었을 때, 한 배열을 해쉬셋에 넣고 나머지 배열의 원소들을 해당 해쉬셋에 존재하는지 검사하는게 당연히 더 빠르다.(정렬 알고리즘 시간 복잡도 때문.)
쨋든, 두 방식 모두 시간 복잡도가 떨어지는데 어떤 더 나은 방법이 있을까?

### 13. [Easy] Longest-Common-Prefix (18:20) (O/?)
(https://leetcode.com/problems/longest-common-prefix/)

String 배열에서 한 원소를 잡고 해당 원소의 가장 첫 번째 알파벳부터, 다른 문자열들의 같은 인덱스에 같은 알파벳이 존재하는지 체크.  
최악의 경우 모두 같은 문자열 길이에 모두 같은 단어면, 시간 복잡도가 O(n^2)이 될 것 같다. 해서 그런지 시간 복잡도 점수가 낮게 나옴. 성능 향상 시킬 방법을 고려해보자.

### 14. [Easy] String-Matching-In-An-Array (12:18) (O/?)
(https://leetcode.com/problems/string-matching-in-an-array/)

String 배열에서 한 원소 씩 잡고 배열의 나머지 원소에 대해 해당 원소를 포함하는지 검사. 포함하면 리스트에 추가. 위 문제와 마찬가지로 시간 복잡도가 O(n^2)가 되므로 더 좋은 방법 찾아봐야 함.

### 15. [Easy] Valid-Palindrome (28:54) (O) [✓]
(https://leetcode.com/problems/valid-palindrome/)

문자열을 소문자로 변환 후, 투 포인터 사용하여 영숫자를 만나면 각각 정지하여 같은지 비교, 영숫자가 하나라도 있다면 바운더리 내에서 반드시 종료됨. 예외 하나는 영숫자가 하나도 없을 때인데 이러면 포인터가 바운더리를 벗어나게 되어 예외 처리 해줬음. 시간 복잡도 O(n).  
또 바운더리 벗어나는 예외 처리에 시간 소모.  
조건 처리를 좀 더 명확하게 할 필요 있어보임.  
+) 새로운 문자열에 입력 문자열을 lowerCase 해서 사용하면 공간 복잡도가 O(n)이 되므로, 각 영숫자를 비교할 때만 lowerCase를 하면 O(1)로 해결할 수 있다.
