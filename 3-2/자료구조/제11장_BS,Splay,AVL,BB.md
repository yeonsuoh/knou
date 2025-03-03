# 11강. BS, Splay, AVL, BB


## 1. 이진 탐색 트리(BS 트리)
* 이진 탐색 트리 : 빠르게 탐색할 수 있도록 구성한 이진 트리
* 키 : 각 노드를 식별하기 위해 별도의 간단한 이름을 붙인 것
* 트리의 높이 : 노드가 가질 수 있는 가장 높은 레벨에 1을 더한 값으로 루트로부터 잎까지 가장 긴 경로 길이
* 트리의 무게 : 트리에 속한 잎 노드의 개수

### 1.1 BS 트리 순회
* 전위, 중위, 후위 순회로 모든 정점을 차례로 순회할 수 있고, 트리 내의 특정 정점을 탐색할 수도 있다.

### 1.2 BS 트리 탐색
1. 트리가 비어 있다면 탐색 실패, 아니면 k와 현재 루트 노드의 키값(ki)을 비교한다.
2. k = ki이면 탐색 성공, 이때 찾은 정점은 vi이다.
3. k < ki이면 vi의 왼쪽 서브트리 탐색
4. k > ki이면 vi의 오른족 서브트리 탐색

### 1.3 BS 트리 삽입 및 삭제
* 삽입
  * 새 노드는 항상 잎으로 삽입

* 삭제
  * 한쪽 서브트리가 NULl인, 자식을 하나만 갖는 노드를 삭제하는 경우
    * 그 노드의 NULL이 아닌 서브트리의 루트를 삭제한 노드를 가리키던 포인터에 할당
    * 두 개의 서브 트리를 가진 경우
    * 루트를 삭제하는 경우 

## 2. Splay, AVL, BB 트리

### 2.1 Splay 트리

* Splay 트리 : 자주 탐색하는 키를 가진 노드를 루트에 가깝게 위치하도록 구성한 이진 탐색 트리
* Zig
* Zig-Zig
* Zig-Zag

### 2.2 AVL 트리

* AVL 트리 : 노드 v1의 왼쪽 서브트리 높이와 v2의 오른쪽 서브트리 높이가 최대 1만큼 차이가 난다는 조건을 만족하는 트리

### 2.3 BB 트리
* 무게가 균형 잡힌 트리 : 각 노드의 양쪽 서브트리 무게가 균형을 유지하는 트리