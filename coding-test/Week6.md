### 1. [Medium] Word Break (X)
(https://leetcode.com/problems/word-break/)

못 푼 이유: 트라이에 대해 공부하자.  

### 2. [Medium] 3Sum (X)
(https://leetcode.com/problems/3sum/)

못 푼 이유: 알고리즘 고안 실패.  

### 3. [Medium] Smallest String With A Given Numeric Value (X)
(https://leetcode.com/problems/smallest-string-with-a-given-numeric-value/)

못 푼 이유: 알고리즘 못 찾음.

### 4. [Medium] Maximum Subarray (23:05) (O)
(https://leetcode.com/problems/maximum-subarray/)

배열의 각 원소까지 연속 부분 배열의 최댓값은, 이전까지의 값이 음수였다면 본인 값으로 갱신하고 양수였다면 더하고 넘어가면 됨. 따라서 이전 위치까지의 합이 양수면 현재 값을 더한 뒤 해당 자리에 기록하고 다음 값으로 넘어가고, 그렇지 않으면 현재 값을 그대로 두고 넘어가면서 기록된 값과 최댓값을 비교하여 갱신하면서 모든 원소를 한 번씩 탐색하면 됨.  
Follow-up의 요구 사항인 분할 정복은 다음에 시도해보는 걸로.

### 5. [Medium] Interleaving String (X) [✓]
(https://leetcode.com/problems/interleaving-string/)

lcs에 관련된 문제 같은데 명확한 알고리즘 파악을 못한 것 같음.  
+) 힌트 보고 이해한 알고리즘은, dp[i][j]의 값은 s1의 앞 문자열 i개와 s2의 앞문자열 j개를 이용해서 s3의 앞 문자열 i+j개를 만들 수 있는가임. 그러기 위해선 s3의 i+j-1개의 문자에서 s1의 i번째 문자를 추가하거나 s2의 j번째 문자를 추가해야 함. 그러므로 s1의 i번째가 만약 s3의 i+j-1과 같으면 s1의 i번째 문자가 추가될 수 있는 것이므로 dp[i-1][j] 값을 보고 0이 아니면 +1을 하고 s2의 j번째 문자가 s3의 i+j-1과 같으면 dp[i][j-1] 값을 보고 0이 아니면 +1을 한다. 그런데 s1의 i번째와 s2의 j번째 문자가 같을 수 있음. 이때는 순서에 따라 잘못 갱신될 수도 있으므로 dp[i][j]가 0일 때만 갱신함.  

   0  d  b  b  c  a  
0  0  0  0  0  0  0  
a  1  0  0  0  0  0  
a  2  3  4  5  6  0  
b  0  4  5  0  7  0  
c  0  0  6  7  8  9  
c  0  0  0  8  0 10  

++) 위 상태를 int로 저장하는라 조건문이 쓸데없이 길어졌는데, 필요한건 boolean 값이므로(인지 아닌지만 판단하면 됨.) s3의 i+j-1에 s1의 i번째 문자가 들어가면 dp[i-1][j]의 상태를 확인하면 되고, s2의 j번째 문자가 들어가면 dp[i][j-1]의 상태를 확인하면 됨. 만약 둘 다 가능하다면 true로 갱신하면 됨. 그리고 dp[s1.length()][s2.length()]의 상태를 확인함.

true : 1  
false : 0  

   0  d  b  b  c  a  
0  1  0  0  0  0  0  
a  1  0  0  0  0  0  
a  1  1  1  1  1  0  
b  0  1  1  0  1  0  
c  0  0  1  1  1  1  
c  0  0  0  1  0  1  

코드는 깔끔해졌지만 시간 복잡도가 O(s1+s2)인데 더 좋은 방법이 있을 것 같다.

### 6. [Hard] Best Time To Buy And Sell Stock III (X/?) [✓]
(https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iii/)

못 푼 이유: 알고리즘 고안 실패.  
+) 힌트 받아 해결. 최대 두번 살 수 있기 때문에 i번 째를 기준으로 0~i-1에서 얻을 수 있는 최대와 i~n에서 얻을 수 있는 최대를 각각 계산해 기록해놓고 두 개의 합이 최대가 되는 i를 찾는다.  
ex)  
prices  3   3   5   0   0   3   1   100 1   99  5   10  3   10  
left    0   0   2   2   2   3   3   100 100 100 100 100 100 100  
right   100 100 100 100 100 99  99  98  7   7   7   7   7   0  

++) 배열 없이 O(1)로 해결할 수 있다고 한다. 추후에 도전.

### 7. [Medium] Coin Change (X/O) [✓]
(https://leetcode.com/problems/coin-change/)

못 푼 이유: 시간 내에 해결 실패.  
시간 끝나고 점화식 세운대로 코드를 짜봤는데, dp의 상태를 정확하게 표현하지 못해 코드가 지저분하고 조건문이 많아짐.  
상태 표현을 잘해보려고 노력하는게 좋아보임.  

### 8. [Medium] Remove Duplicates From Sorted List II (X)  
(https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/)

못 푼 이유: linked list에 대한 이해 부족 + 머리가 안돌아간 거 같은데?  
방법은 맞는데 멍청하게 코드를 못짰네? 이걸 못푸네?  

### 9. [Medium] Reverse Words In A String (32:18) (O) [✓]  
(https://leetcode.com/problems/reverse-words-in-a-string/)  

먼저 문자열을 strip하여 앞뒤 공백을 자르고, for문 돌려서 공백 만나면 앞에서부터 공백 전까지 잘라서 list에 넣음. 그리고 앞 공백 잘라서 다시 문자열에 넣음. 이후 list 뒤부터 훑으면서 단어 추가하고 공백 넣고 마지막 공백 없앤 후 반환. substring의 연산 때문에 시간 복잡도가 높게 나옴.  
+) 핵심은 투포인터를 이용해 인덱스만 움직여 단어를 집어 넣는 것. => O(n), O(1)로 해결 가능.

### 10. [Easy] Happy Number (19:10) (O) [✓]  
(https://leetcode.com/problems/happy-number/)

n을 한 자리씩 제곱한 놈을 sum에다가 더해서 HashSet에 저장하고 HashSet에 있는 놈이 나오믄 false 반환. 1이 되면 true 반환.  
+) 추가로 순환 문제에서 fast 포인터와 slow 포인터를 두고 투포인터로 순환을 체크하는 방식도 가능.  

### 11. [Medium] Spiral Matrix (X)  
(https://leetcode.com/problems/spiral-matrix/)

못 푼 이유: 시간 내 코드 작성 실패.  
flag를 두어 상하와 좌우를 번갈아가면서 탐색할 수 있도록 하고 한 번 탐색할 때마다 상하, 좌우를 각각 한 칸씩 줄어들게 하며 탐색한다.  
거의 다 짠 것 같은데 코드에 빈틈이 있는 것 같다.  

### 12. [Medium] Clone Graph (41:17) (O) [✓] 
(https://leetcode.com/problems/clone-graph/)

노드의 간선(A)에 연결된 노드(B)들을 각 clone 노드(B의 clone)를 만들어(hash table에 추가) clone 노드(A의 clone)의 간선에 연결, 해당 노드와 clone 노드를 대상으로 같은 동작을 재귀적으로 실행함. 이때 hash table에 추가된 노드라면 바로 반환. 시간 복잡도 O(v+e), 공간 복잡도 O(v).  

### 13. [Medium] Redundant Connection (X)
(https://leetcode.com/problems/redundant-connection/)

못 푼 이유: 알고리즘 못 떠올림.
모든 노드를 각각의 집합으로 초기화하고, 추가되는 간선에 따라 각 노드들을 같은 집합으로 묶어줌. 이때 이미 같은 집합이었던 노드들의 간선이 추가된다면 사이클이 생김.  

### 14. [Medium] Network Delay Time (X)
(https://leetcode.com/problems/network-delay-time/)

못 푼 이유: 알고리즘 X.
위와 같이 집합으로 연관지어 해결해보려 했는데, 이런 방식이 아닌 것 같음.
