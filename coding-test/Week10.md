### 1. [Medium] Gas Station (X)
(https://leetcode.com/problems/gas-station/)

못 푼 이유: 처음 알고리즘은 시간 초과 발생.  
i에서 다음 목적지까지 갈 때 가스 상태 -> prev(가지고 있던 가스 상태) + gas[i] -cost[i]라 볼 수 있음. 근데 각 i에서 만족해야 할 조건은 현재 가스 상태 >= 0, 즉, prev + gas[i] - cost[i] >= 0를 만족해야 함. 그런데 모든 i를 시작점으로 잡고 가능한지 판별한다면 O(n^2)로 시간 초과 발생.  
+) 또 그리디에 맞았다.

### 2. [Easy] Unique Email Addresses (22:28) (O) [✓]
(https://leetcode.com/problems/unique-email-addresses/)

HashMap에 키를 도메인, 값을 hashSet으로 생성하여, 도메인에 대하여 로컬 이름을 검증하는 식으로 진행. 로컬 이름은 String 함수를 이용하여 적절히 자르기.

### 3. [Medium] Find All Anagrams In A String (X) [✓]
(https://leetcode.com/problems/find-all-anagrams-in-a-string/)

못 푼 이유: 알고리즘 못 찾음.  
개수는 같고, 순서만 다르기 때문에 먼저 p에 들어있는 알파벳의 각 개수를 체크해야 한다고 생각했음. 그리고 p 길이의 윈도우를 s에서 보면서 알파벳 개수를 하나씩 -하고, 길이가 p일 때 체크되었던 모든 알파벳의 개수가 0이 돼야 한다고 생각했음. p에 존재하지 않는 문자를 만나면 개수를 처음부터 다시 세어야하고, 윈도우의 길이를 넘어서면 윈도우 제일 앞쪽에 있던 문자의 개수를 하나 다시 복구 시켜야 함. 윈도우 안에서 한 알파벳의 개수가 초과되면 그 자리에서부터 다시 세어야 하는데 이 알고리즘으로 코드를 짜다보니 조건문이랑 코드가 너무 복잡해짐.  
+) 고정 길이 슬라이딩 윈도우에 대한 문제인데, 처음봐서 그런가 뭔가 개념 자체는 어렵진 않은데 상당히 골아팠음.

### 4. [Medium] Group Anagrams (21:18) (O)
(https://leetcode.com/problems/group-anagrams/)

같은 그룹의 애너그램을 어떻게 해싱할 것인가가 핵심. 고민하다가 주어진 문자열을 정렬한 것을 키로 해싱하기로 결정. 문자열을 char배열로 바꾼 후 정렬하여 해쉬 테이블에 없으면 추가하고 값은 리스트의 인덱스를 저장. 따라서 해쉬 테이블에 있는 문자열은 같은 애너그램 그룹이므로 값을 받아와 해당 리스트의 인덱스에 추가하면 됨. 무언가 또 쓸데없는 공간 낭비가 발생한 느낌. 시간 복잡도는 O(n*llogl).  
+) 리스트를 인덱스로 재접근하는 것이 아니라 해쉬 테이블에 해당 리스트를 바로 저장해두면 중간 과정 생략 가능.  
++) 직렬화하는 방법들을 고려해보자.

### 5. [Medium] Divide Player Into Teams Of Equal Skill (29:10) (O) [✓]
(https://leetcode.com/problems/divide-players-into-teams-of-equal-skill/)

먼저 해쉬 테이블에 숫자들의 개수를 저장. 각 팀의 능력치 합 = 모든 선수들 능력치 총합 / (전체 선수 숫자 / 2). 1~1000까지 돌며, i 능력치의 선수가 1명 이상이면 teamSum - i의 선수도 같은 숫자로 존재해야 함. 하지만 같은 능력치의 선수가 같은 팀에 배치되는 상황을 먼저 체크해야 하므로 같은 능력치의 선수의 수가 홀수면 -1 반환. 짝수면 chemistry에 반영. 그 외의 경우도 chemistry에 더해주는데 이 때 teamSum - i번째 해쉬 테이블을 초기화하면서 가야 teamSum -i번째에 갔을 때도 이미 체크된 것을 반영할 수 있음.  

### 6. [Easy] N-th Tribonacci Number (04:08) (O) [✓]
(https://leetcode.com/problems/n-th-tribonacci-number/)

bottom-up tabulation.

### 7. [Easy] Power Of Four (X) [✓]
(https://leetcode.com/problems/power-of-four/)

못 푼 이유: 제한 시간 내 follow-up 해결 실패.  
비트 조건이 제일 앞이 1이 되고, 0의 개수는 2의 배수여야 함.  
+) 비트 연산을 graceful하게 하면 됨.
