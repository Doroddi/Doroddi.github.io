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

### 6. [Easy] Maximum Value Of An Ordered Triplet I (18:29) (O)
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

### 9. [Medium] Simplify Path (X/O)
(https://leetcode.com/problems/simplify-path/)

못 푼 이유: 제한 시간 내 못 품.  
코드가 진짜 꼴뵈기 싫을 정도로 더럽다.

