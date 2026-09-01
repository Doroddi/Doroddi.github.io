### 1. [Easy] Excel Sheet Column Number (06:43) (O) [✓]
(https://leetcode.com/problems/excel-sheet-column-number/)

26진수라고 생각하면 끝(진수는 0-25, 현재 문제는 1-26의 표현 차이).

### 2. [Medium] Repeated DNA Sequences (X/O) [✓]
(https://leetcode.com/problems/repeated-dna-sequences/)

못 푼 이유: 감이 안와서 힌트 봄. (Sliding Window, Hash Table)  
10칸짜리 윈도우를 s의 첫 문자부터 밀며 나오는 모든 10개짜리 String을 Hash Table에 없다면 저장. 만약 있다면 2번 존재한다는 의미이므로 답에 추가. 시간 복잡도는 O(n * 10(substring 함수))이므로 O(n)이라고 생각하고, 공간 복잡도는 O(10 * n)이므로 공간 복잡도도 O(n)이라 생각. 헌데 시간, 공간 낮게 나옴.  
+) 문자가 A, T, C, G밖에 없고 길이도 10밖에 되지 않으므로 정수로 압축이 가능함. 4종류이므로 2비트 x 10개 해서 20비트의 정수로 10개의 문자열을 표현 가능. 이렇게 문자열을 정수로 압축함으로써 문자열 생성, 저장, 해싱 비용을 줄일 수 있고, 상태 범위가 작다면 HashMap조차 배열로 대체 가능.

### 3. [Medium] Decode String (X) [✓]
(https://leetcode.com/problems/decode-string/)

못 푼 이유: String 관련 구현이 항상 어려움.  
상태 분리를 잘하는 것이 중요할 듯.

### 4. [Easy] Isomorphic Strings (10:17) (O) [✓]
(https://leetcode.com/problems/isomorphic-strings/)

s에서 t로 매핑되는 문자를 해쉬맵에 기록. t에서도 s로 매핑되게 해쉬맵에 기록해두고 s의 해쉬맵에 없을 때 S->T로 기록 + T에 없으면 T->S 기록. S->T는 없는데 T->S가 있다면 똑같이 매핑되지 않았다는 의미이므로 false, S->T에 있는데 현재 T의 문자와 S->T로 매핑된 문자가 다르면 false.

### 5. [Medium] Bulls and Cows (23:45) (O) [✓]
(https://leetcode.com/problems/bulls-and-cows/)

야구 게임에서 힌트를 구현하라. 숫자 범위가 0\~9이므로 10짜리 인트 배열을 만들어 secret에 있는 모든 숫자의 개수를 각각 수집. 먼저 루프를 돌며 bulls는 secret과 guess에서의 자리와 숫자가 모두 같으면 값을 증가 시킴. 이후 다시 루프를 돌며 guess의 숫자 개수가 남아있으면서 bulls가 아닌 애들을 cows로 카운트 시킴. 총 3번의 루프를 도는데 좀 더 효율적인 방법이 있지 않을까 하는 고민.  
+) 만약 secret과 guess에 있는 bulls를 제외한 수들을 기록 해둔다면 그 수들은 모두 cows에 해당될 수 있는 수임. 따라서 각 secret과 guess의 0~9 배열 중 더 작은 수를 cows에 반영하면 guess에 더 적게 존재했더라도 secret에 매칭이되고, secret에 더 적게 존재했더라도 그만큼만 반영되면 됨.

### 6. [Easy] Backspace String Compare (34:50) (O) [✓]
(https://leetcode.com/problems/backspace-string-compare/)

스택으로 하면 '#'이 나올 때마다 스택에 저장되어있는 친구를 팝한 다음에 스택에 남은 애들끼리 비교하면 끝. follow up을 해결하기 위해 투 포인터를 사용하여 뒤에서부터 읽었음. 문자를 만나면 서로 비교하고 #을 만나면 #의 개수를 저장 후 포인터 전진. 다시 문자를 만났을 때 #의 개수가 남아있다면 #의 개수를 감소시키고 포인터 전진. 그러다 보면 어느 문자에서 멈출 것이고 멈춘 문자들에서 비교하는 방식으로 하면 O(n)에 O(1)로 해결 가능하다. 근데 조건을 명확하게 구분을 못해서 조건문이 주렁주렁달린 가독성 떨어지는 코드가 돼버린게 아쉬움.  
+) 두 포인터가 음수일 때의 조건만 깔끔하게 처리하면 좀 더 가독성 좋은 코드가 됨.

