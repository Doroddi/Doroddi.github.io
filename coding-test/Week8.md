### 1. [Easy] Excel Sheet Column Number (06:43) (O) [✓]
(https://leetcode.com/problems/excel-sheet-column-number/)

26진수라고 생각하면 끝(진수는 0~25, 현재 문제는 1~26의 표현 차이).

### 2. [Medium] Repeated DNA Sequences (X/O) [✓]
(https://leetcode.com/problems/repeated-dna-sequences/)

못 푼 이유: 감이 안와서 힌트 봄. (Sliding Window, Hash Table)  
10칸짜리 윈도우를 s의 첫 문자부터 밀며 나오는 모든 10개짜리 String을 Hash Table에 없다면 저장. 만약 있다면 2번 존재한다는 의미이므로 답에 추가. 시간 복잡도는 O(n * 10(substring 함수))이므로 O(n)이라고 생각하고, 공간 복잡도는 O(10 * n)이므로 공간 복잡도도 O(n)이라 생각. 헌데 시간, 공간 낮게 나옴.  
+) 문자가 A, T, C, G밖에 없고 길이도 10밖에 되지 않으므로 정수로 압축이 가능함. 4종류이므로 2비트 x 10개 해서 20비트의 정수로 10개의 문자열을 표현 가능. 이렇게 문자열을 정수로 압축함으로써 문자열 생성, 저장, 해싱 비용을 줄일 수 있고, 상태 범위가 작다면 HashMap조차 배열로 대체 가능.

### 3. [Medium] 
