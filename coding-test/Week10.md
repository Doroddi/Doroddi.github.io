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

### 8. [Medium] Zigzag Conversion (30:46) (O) [✓]
(https://leetcode.com/problems/zigzag-conversion/)

지그재그의 규칙을 찾음. 첫줄은 numRows * 2 - 2로 인덱스가 진행. 그다음 줄부터는 a + b = numRows * 2 - 2인 a, b가 번갈아가면서 진행되는데 각 a, b는 줄이 넘어가면서 -2, +2가 됨. 예를 들어, 첫 줄이 8개씩 인덱스가 넘어갔다면, 두번 째 줄은 6개가 넘어가고 2개가 넘어가고, 셋째 줄은 4개 넘어가 4개 넘어가고, 다음은 2, 6, 다시 8개씩 넘어감. 이걸 조건문으로 정리하고 번갈아 가는 표시는 flag를 두어 분기를 나누었음.

### 9. [Medium] Count And Say (16:08) (O) [✓]
(https://leetcode.com/problems/count-and-say/)

베르나르 베르베르의 개미 수열. 이전 상태 기억해놓고 분기나눠서 현재 상태 만들기.

### 10. [Medium] Merge In Between Linked Lists (20:29) (O) [✓]
(https://leetcode.com/problems/merge-in-between-linked-lists/)

개념은 쉬운데, 각 노드를 가리키는 포인터에 대한 이해도가 떨어지는 것 같음. 새로운 노드를 만들어서 해당 원래 있던 노드를 가리키면 두 개가 같은 노드를 바라보게 됨. 그렇기 때문에 새로운 노드를 만들어서 새로운 노드의 다음 노드가 원래 노드를 가리키게 만든다?  
+) 제대로 잘못 이해하고 있었다. 그냥 포인터 만들어서 해당 객체를 바라보게 만들면 원래 그 객체를 바라보던 포인터가 다른 곳을 바라봐도, 새로 만든 포인터는 원래 객체를 바라본다. 포인터 변수를 조작하는 것과 next를 바꾸어 객체 구조 자체를 조작하는 것에서 이해도가 낮았던듯.

### 11. [Easy] Fibonacci Number (03:26) (O) [✓]
(https://leetcode.com/problems/fibonacci-number/)

피보나치 수열.

### 12. [Medium] Lowest Common Ancestor Of A Binary Tree (42:09) (O) [✓]
(https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/)

많이 빙빙 돎. 상태는 내가 p 또는 q면 자식을 볼 필요 없이 내가 조상, p 또는 q가 아니라면 왼쪽 자식에 둘 다 있거나 오른쪽 자식 둘 다 있거나 각각 하나 씩 있거나 이렇게 세 가지로 나뉨. 부모한테 넘겨줘야할 값은 자식부터 올라온 노드. 자식에게 타겟이 없었다면 null이 올라올 것. 왼쪽 자식과 오른쪽 자식 중 null 있다면 나머지 한 쪽에 두 개가 다 있다는 뜻. 각각 하나씩 있었다면 자기 자신이 조상. 뭔가 정리가 어수선함.  
+) 정리를 좀 하면, p 또는 q 노드를 찾으면 바로 반환. 자식 중 한쪽에서만 발견되면 그 자식을 반환. 양쪽에서 발견되면 본인을 반환. leaf는 null반환.

### 13. [Medium] Maximal Square (X)
(https://leetcode.com/problems/maximal-square/)

못 푼 이유: 알고리즘 방향이 감이 잘 안옴.  
인덱스를 대각으로 늘렸을 때, 그 칸이 1이면 나머지 칸들에 대해서 0인지 1인지 판단을 해야 하고 모두 1이었다면 정사각형이므로 대각으로 늘린 차원의 제곱이 곧 넓이가 되므로 이를 갱신해주면 됨. 만약 대각으로 늘린 칸이 0이었다면 이전 칸도 해당 칸 이전 차원의 정사각형에 대해서는 모두 0으로 만들어도 된다고 생각했음. 왜냐하면 그 전 차원의 정사각형 크기보다 새로운 1들이 만들 수 있는 정사각형의 크기가 더 커질 수 없기 때문에. 요정도까진 생각은 했는데 뭔가 부족한 부분이 많다.  

### 14. 숫자 문자열과 영단어 (11:39) (O) [✓]
(https://school.programmers.co.kr/learn/courses/30/lessons/81301?language=java)

각 숫자 문자열을 키로 정수에 매핑 시켜놓고, 주어진 문자열에서 잘못된 문자열은 존재하지 않기 때문에 키를 만나면 답에 더해주고 다시 문자열을 탐색하는 방식으로 진행.  
+) 문자열 배열을 만들어놓고 replace하면 코드 구현도 자체는 낮아짐.

### 15. 오프채팅방 (26:00) (O) [✓]
(https://school.programmers.co.kr/learn/courses/30/lessons/42888)

해쉬맵에 "Enter"일 때 유저 아이디를 키로 닉네임을 저장. "Change"일 때 유저 아이디를 변경. "Enter"와 "Leave"에 해당하는 문자열은 큐에 담아놓고 마지막에 문자열을 생성하면서 해쉬맵에 들어있는 유저 아이디를 키로 닉네임을 찾아 리스트에 담는다.  
+) 간단히 2-pass하면 큐 비용 절약 가능. 하지만 split 비용 추가로 발생할 수 있음. 인덱스를 활용하면 split 비용까지 최적화 가능.
