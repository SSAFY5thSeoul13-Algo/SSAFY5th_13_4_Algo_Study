[풀이]
- 중복해서 덩치를 비교하지 않게, grade라는 일차원 배열을 이용하여 구현하였습니다.<br>
이중 for문을 돌며 두사람 중 덩치가 작은 사람의 grade를 증가시켜서 순위를 정해주었습니다.
- 누가 덩치가 큰지를 반환하는 isBig함수를 구현하였습니다.<br>
몸무게와 키의 차이를 각각 1. 0. -1로 변환하고 다음과 같은 3가지 상태를 반환합니다.
    - 2 : 상대가 큼
    - 0 : 같거나 모름
    - -2 : 내가 더큼
 
[막힌점]
- 덩치가 동일한 경우를 생각하지 못하였습니다.

[결과]
- 공간 : 11572KB
- 시간 : 84ms