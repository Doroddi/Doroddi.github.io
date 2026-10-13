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

