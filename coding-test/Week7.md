### 1. Minimum Cost For Tickets (X)
(https://leetcode.com/problems/minimum-cost-for-tickets/)

못 푼 이유: 알고리즘을 찾지 못함.

### 2. [Easy] Minimum Sum Of Mountain Triplets I (20:23) [✓]
(https://leetcode.com/problems/minimum-sum-of-mountain-triplets-i/)

배열의 각 원소에서 좌우로 뻗어 나가면서 조건을 만족하는 삼중항을 찾고 최솟값을 갱신하는 방식으로 O(n^2)로 풀었지만, 배열의 최솟값을 가지고 두 파트로 나눈 후 각각 최솟값이 되는 삼중항을 찾는 방식도 가능할 것이라 생각. 하지만 코드 구현이 너무 복잡해짐.  
+) 각 원소에서의 왼쪽에서의 최솟값과 오른쪽에서의 최솟값을 저장하는 배열들을 생성하여 최솟값을 갱신하면 O(n)까지 가능. 대신 공간 복잡도도 O(n).

### 3. [Medium] Accounts Merge (X)
(https://leetcode.com/problems/accounts-merge/)

못 푼 이유: 감을 0.1도 못 잡음.  
너무너무너무너무나도 어려움.

### 4. [Easy] Degree Of An Array (31:33) (O) [✓]
(https://leetcode.com/problems/degree-of-an-array/)

차수가 높은 것 중 연속 부분 배열의 길이가 가장 짧은 것을 찾는 문제. 배열의 각 원소의 종류에 따라 hashMap에 정보를 저장했음. HashMap에 저장하는 정보는 등장 횟수, 처음 등장한 위치, 해당 원소가 만드는 연속 부분 배열의 길이. 배열을 순회하며 같은 원소가 등장하면 HashMap의 해당 정보들을 업데이트 시키고 HashMap에 저장된 원소들의 정보들 중 차수가 가장 높은 애들 가운데 연속 부분 배열의 길이가 가장 짧은 값을 반환하였음.  
를 겁~~~~나 억지스럽게 구현했음. 시간 복잡도가 O(n)인데, 점수가 한 없이 낮게 나오는 것 보면 쓰잘데 없는 함수 사용으로 인한 시간 비용 증가이지 않을까?  
+) 쓸데없는 상태를 저장하고 그로인해 불필요한 자료구조를 생성하다 보니 느려지는 것이었음. 이러한 부분을 성장 시킬 필요가 있어보임.

### 5. [
