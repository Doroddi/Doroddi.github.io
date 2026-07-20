### 1. [easy] Search-Insert-Position (3:27) (O) [✓]
(https://leetcode.com/problems/search-insert-position/)

이진 탐색 알고리즘에 따라 타겟을 찾으면 해당 index를 반환, 찾지 못한다면 들어가야할 자리를 반환. Arrays.binarySearch()는 들어가야할 index를 (-( insertion point ) - 1)로 반환함.

### 2. [Medium] Find-First-And-Last-Position-Of-Element-In-Sorted-Array (20:58) (O) [✓]
(https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/)

Upper Bound와 Lower Bound를 찾는 문제. 기본 개념은 Upper Bound는 target보다 크거나 같은 수를 찾아가면서 처음으로 target보다 큰 수를 찾으면 그 index - 1이 중복된 target의 가장 오른쪽. Lower Bound는 작거나 같은수를 찾아가면 찾은 index가 target의 가장 왼쪽.  
이 때 해당 배열에 숫자가 없을 때 Upper Bound는 최종 (index - 1)과 target이 같은지 비교하면 되고, Upper Bound에 존재하지 않으면 당연히 Lower Bound를 찾을 때 없을 것이므로 중복 검사할 필요는 없음.  
더하여 배열의 길이가 0일 때와 1일 때 발생하는 배열 인덱스 정도 고려 정도?

