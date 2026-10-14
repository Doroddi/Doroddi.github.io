### 1. [Medium] Reorganize String (O)
(https://leetcode.com/problems/reorganize-string/)

그리디.

### 2. [Easy] Number Of Recent Calls (07:08) (O)
(https://leetcode.com/problems/number-of-recent-calls/)

큐.

### 3. [Medium] Count Sub Ilands (X)
(https://leetcode.com/problems/count-sub-islands/)

DFS(재귀), BFS(큐 반복문).

### 4. [Medium] Subarray Product Less Than K (X)
(https://leetcode.com/problems/subarray-product-less-than-k/)

슬라이딩 윈도우. 알고리즘은 찾았는데 아직 구현이 미숙함.  
+) 상태 정의만 한다면 코드가 매우매우 간결해짐.

### 5. [Easy] Symmetric Tree (18:27) (O)
(https://leetcode.com/problems/symmetric-tree/)

노드 자식들의 바깥쪽(a.left, b.right) 값과 안쪽(a.right, b.left) 값이 같은지 재귀적으로 탐색.

### 6. [Medium] Generate Parentheses (X)
(https://leetcode.com/problems/generate-parentheses/)

백트래킹. 각 단계에서 (, ) 둘 중 하나를 선택해야 하는데 (는 n보다 작으면 추가 가능, )는 (의 개수보다 작으면 추가 가능하다는 조건을 지켜야 함.

### 7. [Easy] Assign Cookies (11:55) (O)
(https://leetcode.com/problems/assign-cookies/)

정렬 후 그리디하게 만족도가 낮은 아이한테 조건을 만족하는 최소 쿠키부터 배분함.

### 8. [Medium] My Calendar I (23:05) (O/O)
(https://leetcode.com/problems/my-calendar-i/)

정렬되지 않은 모든 timetable에 대해 시간 조건 검사를 하고 통과했으면 추가. -> O(n^2).  
+) TreeSet 자료구조를 이용하여 추가할 때 정렬이 되게 하면 모든 원소를 검사하지 않고 앞 뒤만 확인하여 삽입할 수 있음. 이때 검사 비용 및 삽입 비용이 logn이므로 O(nlogn)까지 줄어듦.

### 9. [Medium] House Robber II (X)
(https://leetcode.com/problems/house-robber-ii/)

House Robber I과 같은 접근이지만 이번에는 원형이라는 조건이 붙음. 여기서 첫 집과 마지막 집을 동시에 선택할 수 없다는 점을 이용하면, 첫 집을 선택했을 때와 마지막 집을 선택했을 때 두 가지 경우에 대해 각각 일렬 구조를 만들 수 있고, 두 가지 경우, 각각으로 나누어 최댓값을 구하면 됌. 아이디어가 좋은 문제.

### 10. Jump Game II (X/O)
(https://leetcode.com/problems/jump-game-ii/)

했던건데, DP인 것도 알겠고 그리디인 것도 알겠는데, 코드가 안 짜진다.  
지금 칸에서 점프할 수 있는 곳 중, 다시 그 칸에서 가장 멀리 갈 수 있는 칸이 나오면 점프한다. 따라서 내가 현재까지 갈 수 있는 최대 범위 안에서 새로운 최대 범위를 갱신시키다가 현재 최대 범위에 이르면 최대 범위를 갱신하고 있던 값으로 바꿔준다.

### 11. Longest Uploaded Prefix (17:38) (O)
(https://leetcode.com/problems/longest-uploaded-prefix/)

비디오를 추가하면 해당 인덱스를 true로 만들고 현재 가장 긴 업로드 시간 인덱스의 값 true가 되었다면 false가 될때까지 업로드 시간을 갱신한다. 시간복잡도 upload 한 번 -> 최대 O(n). 하지만 뒤 비디오 먼저 삽입 시 O(1)이므로 최악의 경우에도 O(n)이라 생각. 공간복잡도 O(n).  
+) 시간복잡도는 upload() 한 번당 분할 상환 O(1).
