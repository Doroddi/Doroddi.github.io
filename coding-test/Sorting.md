### 1. 가장 큰 수 (X) [✓]
(https://school.programmers.co.kr/learn/courses/30/lessons/42746?language=java)

1. 제일 앞 자리 수가 같은 수들끼리 먼저 모음.
2. 각 그룹에서 두 번째 자리 수를 비교하여 내림차순 정렬.(한 자리 수는 그 상태 그대로 다른 수들의 두 번째 자리 수와 비교)
3. 9~0까지의 그룹에서 내림차순으로 정렬된 수를 하나 씩 뽑아서 String으로 만듦.

못 푼 이유: 위의 알고리즘을 생각했는데, 코드로 어떻게 옮겨야할 지 감을 못잡음.
30분 소요했지만, 시간 더 할애하더라도 코드 작성을 하지 못할 것 같아서 넘겼음.

풀이: 두 수를 비교할 때 문자열 상태로 두 수를 합쳐서 비교. 예를 들어, "3"과 "34"를 비교하면 "343"이 "334"보다 크므로 "34"가 앞에 와야함.
이를 이용하여 Array.sort(stringNums, (a, b) -> (b + a).compareTo(a + b))로 한 번에 내림차순 정렬. 두 수를 비교하면 항상 길이도 같기 때문에 문제 생길 것 없음.
문자열 형태로 접근하는 접근 방식을 떠올리지 못한 것이 못푼듯? 

### 2. H-Index (X/O) [✓]
(https://school.programmers.co.kr/learn/courses/30/lessons/42747?language=java)

못 푼 이유: 45분 초과, 문제 자체는 겁나 쉬운데 한 번 잘못된 방식으로 들어가니까 끝 없이 그 굴레에서 벗어나지 못했음. 화장실 한 번 갔다오니까 바로 풂.
*레전드 멍청함 이슈

### 3. Two Sum (X) [✓]
(https://leetcode.com/problems/two-sum/)

못 푼 이유: 45분 초과, 재귀 함수를 통해 접근했는데 일단 재귀 함수 작성이 익숙치 않아 꽤 시간이 걸렸음.
알고리즘 자체는 문제가 없는듯 싶은데 처음 배열을 정렬한 후, 정렬되기 전의 인덱스를 어떻게 찾을까를 해결하지 못해 못푼 것 같음.
+) 원래 배열의 숫자의 인덱스도 추가로 저장하여 해결하면 할 수는 있지만, 정렬하는 과정에서 시간 복잡도가 O(nlogn)이 나오는 듯 싶다.(투 포인터도 가능)

더 나은 풀이: 배열 안의 숫자 하나를 골라 타겟에서 빼면 필요한 나머지 숫자를 알 수 있다. 그 숫자가 배열에 포함되어 있는지만 체크하면 되므로 해쉬맵을 이용하여 현재 숫자와 인덱스를 저장해두면 배열 안의 남은 숫자와 그 짝이 해쉬맵 내에 존재하는가만 찾으면 된다. 시간 복잡도 **O(n)**, 공간 복잡도 **O(n)**.    

### 4. merge-sorted-array (17:22) (O/O) [✓]
(https://leetcode.com/problems/merge-sorted-array/)

뇌 빼고 풀면 겁나 쉽지만 시간 복잡도에서 O(m + n)을 달성할 수 없다.
단순히 두 배열을 합쳐서 정렬 시키면 O((m+n)log(m+n))이 나올 것이다. 처음에 이렇게 했다.

하지만 합병정렬 방식으로 nums1을 복사할 배열 공간을 마련하여 복사된 배열과 nums2를 비교하며 하나씩 집어넣으면 O(m + n)의 시간이 걸린다. 멍청해지지 말자.  
+) 코드 분석 결과 nums1의 빈 뒷공간을 이용하여 큰 수부터 정렬하면 tmpArr를 사용하지 않고 문제를 해결할 수 있으므로 공간 복잡도도 O(m)에서 O(1)로 줄일 수 있다고 한다. 투 포인터 문제

### 5. Majority Element (27:16) (O) [✓]
(https://leetcode.com/problems/majority-element/)

가장 먼저 떠오른 풀이는 정렬 후 앞에서부터 같은 수의 개 수를 세었을 때 다른 수로 바뀐 후까지의 해당 수의 개수가 과반이 되지 않는다면 바뀐 수부터 다시 카운트하고, 만약 남은 수가 절반이라면 해당 수를 바로 반환하도록 작성하였다.  
레전드 멍청한 풀이다. 일단 정렬을 했으면 과반인 값은 중앙에 반드시 존재하게 되므로 능지 이슈 발생.  
+) 코드 분석 결과 Follow-up 기준까지 만족하려면 보이어-무어 알고리즘을 활용하여 후보자 값에서 다른 값을 만날 때마다 같이 제외시키면(모두 제외된 상태에서 후보자와 다른 숫자를 만나면 그 숫자가 다시 후보자가 된다.) 결국 과반인 수는 반드시 남게되므로 O(n)과 O(1)을 손쉽게 만족할 수 있더라.

### 6. Contains-Duplicate (5:22) (O) [✓]
(https://leetcode.com/problems/contains-duplicate/)

정렬 후 앞에서부터 하나씩 읽음. 같은 것 나오면 true 반환, 모두 다 다르면 false 반환.  
시간 복잡도 점수가 낮아서 바로 떠오른 생각은 정렬 중간에 같은 값이면 바로 true 반환하는 방식도 고려해볼만 하지 않나 싶음.  
+) 코드 분석 결과 시간 복잡도를 낮추기 위해선 HashSet을 사용하는 방법이 있지만 공간 복잡도 면에서 단점이 있음.
 
### 7. Valid-Anagram (7:32) (O) [✓]
(https://leetcode.com/problems/valid-anagram/)

각 문자열을 char 배열로 변형 후 정렬한 뒤 앞에서부터 비교. 시간 복잡도는 낫배드, 공간 복잡도는 char 배열 생성으로 인해 낮아진듯?  
+) 알파벳이 26개 밖에 없으므로 두 문자열의 길이가 같을 때 한 문자열에서 각 알파벳 수를 세고 나머지 문자열에서 각 알파벳 수를 빼는 방식으로 하면 O(n)에 O(1)이 가능함.  
Follow-Up에 유니코드까지 고려한다면 더 복잡해질 것으로 보임.

### 8. Set-Mismatch (10:00) (O/?)
(https://leetcode.com/problems/set-mismatch/)

해쉬 방식 (정렬을 하면 O(nlogn)이 되므로 해당 방식 고려(O(n)))  
tempArr 하나 만들어서 각 숫자에 해당하는 칸을 +1로 개수 구하기 2번 나온건 2 안나온건 0이므로 차례대로 출력. 
시간 복잡도를 해치지 않으면서 메모리를 아낄 수 있었을까?

### 9. Top-K-Frequent-Elements (X)
(https://leetcode.com/problems/top-k-frequent-elements/)

머릿속으로는 어떻게 해야할지 생각이 드는데 코드로 옮길 수 없었다.
숫자를 키 값으로 나올 때마다 그 수의 카운트를 올리고 그 윗 등수와 개수 비교를 해서 더 많아졌다면 등수 교환?

### 10. Intersection-Of-Two-Arrays (27:32) (O/?) 
(https://leetcode.com/problems/intersection-of-two-arrays/)

nums1의 수를 해쉬셋에 담는다. nums2를 돌며 해쉬셋에 포함되어있으면 배열에 담는다.  
어떻게 하면 시간 복잡도를 더 좋게 할 수 있을까?

### 11. Kth-Smallest-Element-In-A-Sorted-Matrix (X)
(https://leetcode.com/problems/kth-smallest-element-in-a-sorted-matrix/)

못 푼 이유: 45분 초과. 도저히 공간 복잡도를 O(n^2) 보다 좋게 할 방법이 안 떠오르네.

### 12. Minimum-Number-Of-Arrows-To-Burst-Ballons (X)
(https://leetcode.com/problems/minimum-number-of-arrows-to-burst-balloons/)

못 푼 이유: 감도 못 잡음.

### 13. Array-Partition (11:49) (O/?)
(https://leetcode.com/problems/array-partition/)

어렴풋이 정렬 후 처음 수부터 2칸씩 모두 더하면 답이라는 걸 느끼지만 논리적으로 설명을 몬하겠음. 시간 복잡도도 최악.

### 14. Task-Schedular (X)
(https://leetcode.com/problems/task-scheduler/)

머릿속 알고리즘을 코드로 옮기질 몬하겠음.

### 15. Sort-Array-By-Parity (19:04) (O) [✓]
(https://leetcode.com/problems/sort-array-by-parity/)

투 포인터로 좌, 우에서 조건에 맞는 애들 발견하면 멈춰서 스왑. 시간 복잡도 O(n), 공간복잡도 O(1)

### 16. Sort-Array-By-Parity-II (26:08) (O)
(https://leetcode.com/problems/sort-array-by-parity-ii/)

위문제와 동일하게 투 포인터를 사용해서 짝수 인덱스와 홀수 인덱스를 검사해 잘못 들어간 애들끼리 교환한다.  
추가 배열을 만들지 않고 투포인터를 사용했기 때문에 Follow-up에서 제시한 공간 복잡도 O(1)은 만족하였음.  
최악의 경우에 시간 복잡도가 O(n)인 것 같은데 시간 복잡도를 더 줄일 수 있는 방법이 있는건가?
