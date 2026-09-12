### 1. [Medium] Restore IP Addresses (X/O) [✓]
(https://leetcode.com/problems/restore-ip-addresses/)

못 푼 이유: 제한 시간 내 해결 실패.  
두 가지 상태 보존이 필요한데, 하나는 '.'을 찍는 위치, 그리고 각 구간별 숫자를 모두 지우고 새 숫자를 쓰기. 따라서 숫자 추가 -> '.' 추가 -> 재귀 -> '.' 삭제 -> 숫자 삭제 이 순서로 백트래킹을 진행했음.

### 2. [Easy] Number Of Good Pairs (06:48) (O) [✓]
(https://leetcode.com/problems/number-of-good-pairs/)

배열 인덱스 하나를 잡고 조건을 만족하는 원소들을 반복문으로 모두 찾으면 O(n^2). 하지만 잘 생각해보면 각 숫자들의 조합의 개수를 찾는 문제이기 때문에 숫자들의 개수를 세고, nC2를 모두 더해주면 됨.

### 3. [Solved] [Easy] Complement Of Base 10 Integer (09:50) (O) [✓]
(https://leetcode.com/problems/complement-of-base-10-integer/)

저번에 풀었던 문제이지만, 아마도 저번에도 비트 연산으로 할 수 있는 것을 동일하게 산술 연산으로 구현했던 것 같음. 이번에도 비트 마스킹으로도 해결해 봄.

### 4. [Medium] Beautiful Arrangement (X) [✓]
(https://leetcode.com/problems/beautiful-arrangement/)

못 푼 이유: 시간 초과가 남.  
백트래킹의 핵심 중 하나인 가지치기를 하지 않아서 시간 초과가 났던 것. 사실상 배열의 인덱스와 현재 들어갈 숫자만 필요한 것이기 때문에 배열 자체를 생성할 필요도 없었음. 시간 복잡도 O(n!).

### 5. [Medium] Remove K Digits (X)
(https://leetcode.com/problems/remove-k-digits/)

못 푼 이유: 뭔가 잡힐듯 말듯인데 안 되네.  

### 6. [Easy] Maximum Value Of An Ordered Triplet I (18:29) (O) [✓]
(https://leetcode.com/problems/maximum-value-of-an-ordered-triplet-i/)

왼쪽부터 읽으면서 최댓값을 잡아놓고 각 자리의 원소와의 차를 저장하면 각 자리에서의 차의 값을 기록할 수 있음. 이후 끝에서부터 다시 처음으로 읽으며 최댓값을 잡아놓고 해당 인덱스 이전의 차 값을 곱하면서 최댓값을 찾으면 됨.  
+) 각 자리에서의 차의 값을 기록할 필요도 없이 이전까지의 max 값과 max 차이 값만 가지고 있으면 됌.

### 7. [Medium] Letter Tile Possibilities (43:14) (O) [✓]
(https://leetcode.com/problems/letter-tile-possibilities/)

각 알파벳 자리의 유무를 체크해서 백트래킹을 실시하고 완성된 문자열을 hashset에 넣음. hashset에 없었다면 count를 올리고 아니면 재귀 실행 x.
+) 위는 사실 좋지 못한 풀이고, 이 문제의 핵심은 알파벳의 빈도 수로 구성할 수 있는 문자열을 나타내는 것. 빈도수 표에서 어떤 알파벳을 고르고 재귀로 넘기면 자연스럽게 남은 알파벳들로 문자열을 구성하게 됨. 이렇게 되면 중복을 자연스럽게 방지할 수 있음. 순서가 아닌 각 알파벳의 개수를 가지고 상태를 만들기 때문.

### 8. [Medium] Course Schedule (X)
(https://leetcode.com/problems/course-schedule/)

못 푼 이유: 알고리즘이 떠오르긴 하는데 코드 짜다보면 어디 한 군데 씩 막힘.  
그래프를 만들고 순환이 생기는 구간이 발견되면 false를 반환하는 것 같은데 해결이 안되네. 다시 해봐야 할듯.

### 9. [Medium] Simplify Path (X/O) [✓]
(https://leetcode.com/problems/simplify-path/)

못 푼 이유: 제한 시간 내 못 품.  
코드가 진짜 꼴뵈기 싫을 정도로 더럽다.

### 10. [Easy] Next Greater Element I (X/O) [✓]
(https://leetcode.com/problems/next-greater-element-i/)

못 푼 이유: 제한 시간 내, follow-up을 만족하는 알고리즘을 찾지 못했음.  
문제는 스택을 이용해서 풀고 나서도 왜 정확한 알고리즘인지 설명을 못하겠다는 것. 스택 문제이기 때문에 느낌상 이렇게 해결해야 할 것 같다는 생각만 함.  
+) 오른쪽에서 처음 등장하는 더 큰 값이므로, 왼쪽에서 진행했을 시 해당 숫자보다 더 큰 숫자를 찾기 전까지 그 숫자의 위치를 기억하고 있어야 한다고 생각하여, 방향은 오른쪽에서 왼쪽으로 진행했음. 그러면 오른쪽에서 왼쪽으로 진행했을 때, 두 가지 경우가 발생할 수 있음. 현재 숫자가 이전 숫자보다 작거나 크다. 전자의 경우, 이견 없이 이전 숫자를 hash에 기록하면 됨. 하지만 크면, 이전 숫자의 오른쪽에서 현재 숫자보다 큰 수가 있는지 없는지 판단해야 함. 이를 위해 스택에 현재 숫자들을 채우면서 진행했고, 후자의 경우가 발생했을 시 스택을 팝하면서 더 큰 숫자가 있었는지 확인. 만약에 스택이 빌 때까지 더 큰 숫자가 없으면 -1을 기록. 여기서 걸렸던 건 스택을 팝하는 과정이 현재 숫자의 왼쪽 숫자들에 영향을 줄 수 있냐는 것인데, 현재 숫자의 왼쪽 숫자들이 현재 숫자보다 작으면 항상 현재 숫자보다 작은 범위의 숫자들에서 결정이 날 것이고, 크다면 현재 숫자가 바라본 스택의 탑 숫자(이미 현재 숫자는 스택의 숫자가 더 큰 수인지 확인했기 때문)와 비교될 것이기 때문에 상관이 없음.

### 11. [Medium] Shortest Unsorted Continuous Subarray (X) [✓]
(https://leetcode.com/problems/shortest-unsorted-continuous-subarray/)

못 푼 이유: 감만 옴. 머리가 아픔.  
투포인터 써서 양쪽에서 다가오는데, 숫자가 바뀔 때의 위치를 저장해놔야 함. 왼쪽 포인터가 가리키는 숫자보다 오른쪽 포인터가 가리키는 숫자가 작으면 왼쪽 포인터의 숫자 처음 위치와 오른쪽 포인터 숫자의 처음 위치가 부분 배열의 길이가 됨. 근데 여기에 뭔가 하나가 더 추가돼야 할 것 같은데 그게 너무 머리가 아픔.  
+) 오른쪽으로 가면서 확인해야 할 것은 현재 나온 최대값보다 작은 값이 어디가 마지막인지 체크해야 오른쪽 경계값을 알 수 있고, 왼쪽으로 가면서는 지금까지 나온 최솟값보다 큰 값이 어디가 마지막인지 체크해야 왼쪽 경계값을 알 수 있음. 해당 경계값들의 길이 차가 정렬해야 할 부분 배열의 길이이다.

### 12. [Medium] Broken Calculator (X)
(https://leetcode.com/problems/broken-calculator/)

못 푼 이유: 알고리즘 못 찾음.

### 13. [Medium] Maximum Value Of An Ordered Triplet II (07:54) (O) [✓]
(https://leetcode.com/problems/maximum-value-of-an-ordered-triplet-ii/)

6번과 동일한 문제. 이전에 최적화까지 해놨기 때문에 바로 해결.

### 14. [Medium] Daily temperatures (18:05) (O)
(https://leetcode.com/problems/daily-temperatures)

10번 문제에서 다뤘던 주제이기에 쉽게 해결.

### 15. [
