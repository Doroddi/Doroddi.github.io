## Map
key-value pair들을 저장하는 ADT.  
같은 key를 가지는 pair는 최대 한 개만 존재.  
associative array, dictionary라고 불리기도 함.  

## Hash table(Hash map)
배열과 해시 함수(hash function)를 사용하여 map을 구현한 자료 구조.  
(일반적으로) 상수 시간으로 데이터에 접근하기 때문에 빠름.

## Hash function
임의 크기를 가지는 type의 데이터를 고정된 크기를 가지는 type의 데이터로 변환하는 함수.  
(hash table에서) 임의의 데이터를 정수로 변환하는 함수.

## Hash collision
key는 다른데 hash가 같을 때.  
key도 hash도 다른데 hash % map_capa 결과가 같을 때.

## Hash collision 해결 방법

1. Separate chaining
각 버킷을 linked list로 관리하고, 해시 충돌이 발생했을 때 다음 노드를 체크하는 방식으로 충돌을 피함.

2. Open addressing(linear probing)
배열에서 다음 비어있는 공간에 값을 넣음. 삭제 시 더미를 넣거나 삭제를 표시해야함. 왜냐하면 다음 공간에 저장되어 있는 값을 찾지 못할 수 있기 때문.

## Hash table resizing
데이터가 많이 차게 되면 크기를 늘려줘야 함.  
확장된 크기만큼 해시를 재배치해야 함.
