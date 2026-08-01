### 1. [Easy] Binary-Tree-InOrder-Traversal (17:03) (O/O) [✓]
(https://leetcode.com/problems/binary-tree-inorder-traversal/)

중위 순회란? 왼쪽 자식 > 부모 > 오른쪽 자식 순으로 트리를 순회하는 것. (전위: 부모 > 왼쪽 > 오른쪽 / 후위: 왼쪽 > 오른쪽 > 부모)  
재귀를 사용하면 정말 간단하게 해결 가능함.  
Follow-up에서 제시한 재귀를 사용하지 않고 반복문만으로 해결할 수 있는가에 대해 부모 노드에 대한 기록을 스택에 저장함으로써 해결함.

### 2. [Medium] Minimum-Speed-To-Arrive-On-Time (43:12) (O/?)
(https://leetcode.com/problems/minimum-speed-to-arrive-on-time/)

속도의 범위를 계산해보면 1~10,000,000이므로 이 범위 내의 정수를 이분 탐색하여 시간 내에 도달하면 더 느린 속도를(더 느릴 때도 시간 내에 도달할 수 있는가) 그렇지 않으면 더 빠른 속도를 매겨, 시간 내에 도착하는 양의 정수 속도 중 가장 작은 수, 즉, lower bound를 찾는 문제임. 만약 가장 빠른 속도인 10,000,000(km/h)를 넘어서면 답이 없음으로 처리.  
시간 복잡도는 속도 탐색에 O(logk), 배열 탐색에 O(n)이므로 O(n)이지 않을까 싶음.(logk는 n에 비해 훨씬 작은 수 이므로)
더 빠른 방법은 있을 것 같음. 아니면 연산에서 시간이 오래 걸렸을 수도?

### 3. [Easy] Same-Tree (12:19) (O) [✓]
(https://leetcode.com/problems/same-tree/)

### 4. [Easy] Invert-Binary-Tree (05:55) (O) [✓]
(https://leetcode.com/problems/invert-binary-tree/)

### 5. [Easy] Binary-Tree-Path (32:31) (O) [✓]
(https://leetcode.com/problems/binary-tree-paths/)

### 6. [Easy] Minimum-Absolute-Difference-In-BST (X/O) [✓]
(https://leetcode.com/problems/minimum-absolute-difference-in-bst/)

못 푼 이유 : 시간 초과
중위 순회 문제, BST에서는 중위 순회를 하면 정렬된 배열과 같은 역할을 한다. 트리랑 아직 안 친해서 그런가 코드 작성을 못한 이슈. 재귀나 반복문이나 등등으로 잘하면 되는데 왜이리 코드를 못 짜겠는 것인가. 코딩 스킬 부족.  
그리고 반복문과 재귀 방식 중 재귀 방식이 시간이 훨씬 빠르게 나왔음. 와이?? 시간 복잡도는 똑같은데 스택 조회나 조건 검사 등의 이슈가 아닐지...

### 7. [Easy] Diameter-Of-binary-Tree (X/O) [✓]
(https://leetcode.com/problems/diameter-of-binary-tree/)

못 푼 이유 : 시간 초과
솔직하게 재귀 코드를 짜는 것이 아직 쉽지 않음. 결국 해결은 했는데 시간, 공간 최악.  
일단 알고리즘 자체는 지름이라는 것은 한 노드에서 왼쪽 자식과 오른쪽 자식의 가장 멀리 떨어진 리프 노드까지의 거리의 합이라고 생각하여 N개의 노드에 대해 각 노드를 지나는 지름을 계산함. -> N개의 노드 * 지름 계산(평균 nlogn) = Holy!  
+) 문제의 핵심은 결국 N개의 노드에 대해서 지름 계산을 다시하는 것이 아니라 리프 노드까지의 거리를 계산할 때 지름을 갱신만 해주는 것. 따라서 노드를 방문하는 N번의 실행만 발생하면 되므로 O(n)이 되고, 공간도 O(h)(균형 트리: nlogn, 편향 트리: n)의 복잡도를 가진다.  
트리 재귀에서 생각해야되는 것은 이 함수가 무엇을 부모에게 반환해야 하는가?임. -> 높이를 반환하고 지름은 갱신하는 구조가 적절함.

### 8. [Medium] Unique-Binary-Search-Tree (33:17) (O) [✓]
(https://leetcode.com/problems/unique-binary-search-trees/)

BST이므로 루트에 대해서 왼쪽 자식과 오른쪽 자식의 상태가 명확히 정해짐. 이걸 가지고 점화식을 세울 수 있는데 f(n) = f(n-1) * f(0) + ... + f(0) * f(n-1) (f(0) = 1, f(1) = 1)임.  
그대로 재귀 함수 만들었지만 홀리한 시간 복잡도를 조우할 수 있었음.(O(3^n)ㅋㅋ)   
분명히 이렇게 수학만으로 풀라는게 아닐 것이다.  
+) 이 코드가 문제가 발생하는 이유는 이미 계산된 재귀도 다시 실행되었을 때 또 다시 계산한다는 것임. 이를 해결하기 위해, 메모이제이션을 이용하여 f(k) 값을 메모하면서 메모에 있으면 재귀를 하는 것이 아닌 메모에서 바로 꺼내다 쓰므로 추가 재귀로 인한 시간 복잡도를 줄일 수 있음. 시간 복잡도 O(n^2).  
+) 반복문을 이용해서 Bottom-Up 방식으로도 가능. f(0)과 f(1)로 f(n)까지 만들어가는 과정. 이 역시 시간 복잡도 O(n^2)지만 재귀 호출 스택을 사용하지 않는다는 이점이 있음. 

### 9. [Easy] Symmetric-Tree (X)
(https://leetcode.com/problems/symmetric-tree/)

못 푼 이유 : 걍 못 짜겠음. 머릿속에서 어떻게 코드를 짜야할 지 그려지지가 않음.

### 10. [Medium] Minimum-Time-To-Complete-Trips (24:29) (O/?)
(https://leetcode.com/problems/minimum-time-to-complete-trips/)

2번이랑 동일한 풀이. O(n)같은데 역시 시간 복잡도가 낮게 나온다. O(n)보다 빠를 수가 있나? 혹시 long 연산 때문일까?  
BS 자체는 많이 익숙해진듯. left, right, bound 정도에서 크게 안 벗어나는듯 싶다. 문득 드는 생각은 BS 문제라고 생각하지 않고 접했다면 BS라고 바로 떠올릴 수 있을까?

### 11. [Easy] Maximum-Depth-Of-Binary-Tree (6:55) (O) [✓]
(https://leetcode.com/problems/maximum-depth-of-binary-tree/)

7번 diameter 구하는 문제에서 트리의 최대 높이를 구하는 코드를 작성해봤기 때문에 그 부분만 발췌된 문제.

### 12. [Medium] Binary-Tree-Level-Order-Traversal (29:52) (O) [✓]
(https://leetcode.com/problems/binary-tree-level-order-traversal/)

레전드 상황 발생. 완벽하게 푼듯?  
각 레벨에서 왼쪽 자식의 값부터 투입 재귀도 왼쪽부터 열리므로 형제 노드 중 왼쪽부터 싹싹 들어감.  
+) DFS 방식으로 특정 레벨 별 결과를 구성하는 코드를 짰는데 일반적인 레벨 순회 문제에서는 queue를 이용한 BFS 방식이 정석이라고 함. BFS 풀이도 완.

### 13. [Easy] Conver-Sorted-Array-To-Binary-Search-Tree (12:24) (O) [✓]
(https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/)

정렬된 엄격한 오름차순 배열이므로 배열의 중앙 기준으로 양쪽으로 나누어 left와 right에 넣으면 반드시 균형을 이룰 수 밖에 없음. binary search때 죽도록 했던 것.

### 14. [Medium] Populating-Next-Right-Pointers-In-Each-Node (19:15) (O) [✓]
(https://leetcode.com/problems/populating-next-right-pointers-in-each-node/)

12번 문제에서 이미 해봤던 레벨별 탐색. BFS 방식으로 queue를 이용하여 쉽게 해결. 하지만 queue를 사용하기에 Follow-up의 상수 크기 추가 공간을 해결하지 못했음.  
재귀 방식으로도 풀어보려 했는데 자식의 자식을 잇는 과정을 어떻게 해야할 지 감이 안잡힘. => 개멍청 이슈였음. '현재 노드의 오른쪽 자식을 다음 노드의 왼쪽 자식을 잇는다'라는 것을 생각 못하고 자식의 자식을 잇는다는 생각을 하니까 안되는 거였음.
+) 이미 만들어진 next 포인터를 이용하여 queue를 사용하지 않고 같은 레벨의 노드를 탐색하는 반복문을 통해서도 O(1)로 해결 가능.

### 15. [Easy] Binary-Tree-PreOrder-Traversal (05:18) (O) [✓]
(https://leetcode.com/problems/binary-tree-preorder-traversal/)

1번과 동일. 반복문으로 짜는 것은 참으로 쉽지 않다.

### 16. [Medium] The-Latest-Time-To-Catch-A-Bus (X)
(https://leetcode.com/problems/the-latest-time-to-catch-a-bus/)

못 푼 이유 : 태산.

### 17. Merge-Two-Binary-Trees (29:41) (O) [✓]
(https://leetcode.com/problems/merge-two-binary-trees/)

현재 주어진 노드가 모두 널이 아니라면, 첫 번째 노드에 두 번째 노드 값을 합치고, 자식에 대해서 실행할 것인데 첫 번째 노드에만 자식 노드가 없다면 두 번째 노드의 자식 노드를 가져옴.  
코드가 깔끔하진 않은데 재귀 코드에 더 익숙해질 필요가 있어 보임.

### 18. Search-In-A-Binary-Search-Tree (20:44) (O) [✓]
(https://leetcode.com/problems/search-in-a-binary-search-tree/)

재귀 감 잡는 중.

### 19. Unique-Binary-Search-Tree-II (X)
(https://leetcode.com/problems/unique-binary-search-trees-ii/)

8번의 연장 문제. 8번은 단순 만들 수 있는 BST의 개수였기에, 점화식을 통해서 값만 구하면 됐음. 하지만 이 문제는 그 점화식에 따른 모든 BST를 생성해내야 하는 문제. 어려움.
