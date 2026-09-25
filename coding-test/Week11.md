### 1. [Medium] Find The City With The Smallest Number Of Neighbors At A Threshold Distance (X)
(https://leetcode.com/problems/find-the-city-with-the-smallest-number-of-neighbors-at-a-threshold-distance/)

못 푼 이유: 가닥은 잡혀있는데 디테일한 부분이 기억이 안남.  
+) Dijkstra 알고리즘.

### 2. [Medium] Integer To Roman (23:08) (O) [✓]
(https://leetcode.com/problems/integer-to-roman/)

경우가 많지 않으므로 무식하게 코딩하기.  
+) 보다는 중복된 경우에 대해서 변하는 부분을 데이터로 빼면 코드가 더 가독성있어짐.

### 3. [Medium] Arithmetic Slices (16:09) (O) [✓]
(https://leetcode.com/problems/arithmetic-slices/)

공차가 유지되었다면 count를 세고, 그렇지 않았다면 공차와 count를 리셋한다. 이때 count가 3 이상이면 (count - 2) * (count - 1) / 2개의 등차 배열 조합이 발생하므로 이를 답에 반영하면 된다. 그리고 마지막 등차배열에 대한 처리도 해줘야 함.

### 4. [Medium] Flatten Nested List Iterator (X)
(https://leetcode.com/problems/flatten-nested-list-iterator/)

못 푼 이유: 어떻게 하라는건지 1도 모르겠음.  

### 5. [Medium] Binary Subarrays With Sum (X)
(https://leetcode.com/problems/binary-subarrays-with-sum/)

못 푼 이유: 알고리즘을 완전히 찾지 못함.  
투 포인터를 사용해서 1의 개수가 goal인 윈도우 안에서 양쪽 끝 1의 위치를 찾고, 그 전까지의 0의 개수와 그 이후에 새로 만나는 1 이전의 0의 개수를 세면 0 개수 하나당 2개의 경우가 생기므로 2^(0의 개수)의 연속 배열이 생긴다고 생각했음. 해결하지 못한 부분은 goal이 1일 때? goal이 0일 때는 0의 개수를 n이라 쳤을 때, n * (n + 1) / 2개 만큼의 연속 배열이 발생. 구멍이 더 있을 것이라 생각.  
+) 일단 goal이 0 이상일 때 연속 배열의 개수를 구하는 방식이 잘못됌. 2^(0의 개수)개 생긴다고 생각했는데 생각해보니 있다 없다가 아닌 0 또한 연속 배열로 나타나야하기 때문에 (왼쪽 0의 개수 + 1) * (오른쪽 0의 개수 + 1)만큼 생겨야 함. 그리고 현재 알고리즘으로 했을 때 마지막 경우를 구분해서 마지막 윈도우에 대한 계산을 추가해야 함. 굉장히 비효율적인 알고리즘이라 생각함.
