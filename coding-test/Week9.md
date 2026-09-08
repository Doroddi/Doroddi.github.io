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

### 6. [Medium]
(https://leetcode.com/problems/maximum-value-of-an-ordered-triplet-ii/)
