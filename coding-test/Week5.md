### 1. [Medium] Perfect Squares (37:25) (O)
(https://leetcode.com/problems/perfect-squares/)

정수 n을 만들 수 있는 조합에 사용되는 숫자의 수가 사용되는 완전제곱수에 따라 달라진다 생각. 예를 들어 12를 만들 수 있는 9+1+1+1과 4+4+4 중에서 해는 3이 됨. 13 또한 9+1+1+1+1과 9+4 중 해는 2가 된다. 따라서 완전제곱수에 따라 조합을 따져봐야한다 생각했고, 완전제곱수 k를 하나 잡으면 나머지 수를 만드는 조합은 f(n - k)가 된다. 그러므로 n = 12인 예시를 들었을 때, k=1일 때 f(1)+f(11), k=4일 때 f(4)+f(8), k=9일 때 f(9)+f(3) 이 중 가장 작은 수를 택해 저장하면 된다. 이런식으로 f(n)까지 bottom-up 방식으로 dp 배열을 채워나가는 방식으로 해결했음. 시간복잡도는 n까지 dp 배열을 채우나가므로 n번의 반복문과 각 반복문에서 완전제곱수 하나씩 따지는 횟수인 log(n)번을 합쳐 O(nlog(n))이라 생각. 시간복잡도 점수가 좀 낮게 나옴.

### 2. [Medium] Best Time To Buy And Sell Stock II (O) (14:23)
(https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/)

dp할 때 나왔던 문제의 변형. 주식을 사고 팔면서 최대 이익을 뽑아내는 문제. 가격이 떨어지지 않고 올라가기만 한다면 그 사이 가격들은 내려가기 전 최고가까지 중간에 사고 팔더라도 이익이 같음. 따라서 올라가다가 떨어지는 순간에 팔아야 최대 이익을 볼 수 있음. 떨어지기만 하는 것도 수익이 -이므로 이익에 포함할 필요가 없음. 정리하자면 가격이 떨어지기 전날에 팔고 떨어진날에 사고를 반복하면 최대 이익을 볼 수 있음. 시간복잡도 O(n).

### 3. [Medium] Longest String Chain (X)
(https://leetcode.com/problems/longest-string-chain/)

못 푼 이유: 시간 초과 + 알고리즘?  
기본 생각은 한 문자열이 다른 문자열의 공통 부분 수열이면, 해당 문자열이 현재까지 이룬 최대 체인 + 1이 다른 문자열의 현재까지의 체인이 됨. 이유는 '해당 문자열이 현재까지 이룬 최대 체인' 이 부분이 다른 문자열의 부분이 되므로 그 앞까지 이룬 체인도 모두 포함을 시켜버리기 때문. 그런데 짠 코드에서는 contains 함수가 공통 부분 수열이 아닌 공통 부분 문자열을 반환하기 때문에 답이 틀리게 나오는 것 같음. 좀 더 고려해봐야 할듯?

### 4. [Easy] Complement Of Base 10 Integer (27:53) (O) [✓]
(https://leetcode.com/problems/complement-of-base-10-integer/)

Bitwise 문제. n의 가장 위에 있는 있는 1 비트까지 1로 채워진 수와 XOR 연산을 했음. 단순하게 0이랑 XOR하면 그대로 출력이 되고 이리저리 비트 연산을 해봤는데 더 좋은 방법이 분명 있겠지?

### 5. [Medium] Sort Colors (10:31) (O/?)
(https://leetcode.com/problems/sort-colors/)

3가지 종류 밖에 없으니 세 가지를 각각 수를 센 다음(One-pass) 배열 앞쪽에서부터 개수만큼 채우면 됨(One-pass). O(n)에 O(1). 하지만 2-pass 솔루션임.
Follow-up의 One-pass 솔루션은 투 포인터를 가지고 잘 해보면 될듯 싶으니 더 고민해볼 것.

### 6. [Medium] Rotate List (33:05) (O/?)
(https://leetcode.com/problems/rotate-list/)

연결 리스트를 처음 접해서 좋은 방법으로 풀진 못한 것 같음. 어떻게 뒤에껄 가져와서 앞에다가 이을지 고민을 하다가 deque을 사용하면 쉽게 이을 수 있겠단 생각은 했음. 시간 복잡도 자체는 O(n) 같은데, 부가적인 요소 때문에 시간 점수가 낮게 나오는가 싶음. Or deque을 사용하지 않고 해결하기?쪽이 맞는듯. 그리고 deque을 사용한 순간 공간 복잡도 O(n)이 발생. deque 안쓰고 푸는 것 고려해보기.

### 7. [Medium] Sum Root To Leaf Numbers (12:45) (O) [✓]
(https://leetcode.com/problems/sum-root-to-leaf-numbers/)

재귀로 내려가면서 두 자식이 모두 없으면 현재까지 나온 수를 sum에 합친다. 한 가지 아쉬운 점은 조금 더 가독성 있게 조건을 설정할 수 있지 않았을까?
+) 함수의 값을 반환하도록 하여 재귀함수의 의미를 명확히 정의해볼 것.

### 8. [Easy] Linked List Cycle (06:07) (O/O) [✓]
(https://leetcode.com/problems/linked-list-cycle/)

그냥 노드 수 최대 10000개니까 10000번 돌때 동안 next가 null이 되지 않으면 true로 단순하게 해결하기. O(n)이고 O(1).
+) 하나의 노드를 생성(체크용)해서 모든 노드의 next에 해당 노드를 추가함으로써 생성한 노드를 next를 가지고 있으면 circle이 형성된 것이고, null이 나오면 circle이 형성되지 않은 것.
++) 두 개의 포인터를 두고 이동속도를 다르게 하여 노드를 탐색했을 때, circle이 형성돼있다면 반드시 만날 수 밖에 없음.

### 9. [Easy] Palindrome Linked List (X/O/?)
(https://leetcode.com/problems/palindrome-linked-list/)

못 푼 이유: 적절한 알고리즘을 시간 내에 찾지 못함.  
Linked List는 뒤로 돌아올 수 없으므로 카운트를 세어 중간 지점을 찾고 하나는 중간 지점부터 순행하는 list, 다른 하나는 뒤집어 버린 후 하나씩 val을 비교하여 모두 같으면 palindrome 아니면 false 출력. 뒤집기 코드를 짜는데 오래 걸림 + 좋은 알고리즘도 아닌 것 같고 가독성도 매우 떨어짐.
