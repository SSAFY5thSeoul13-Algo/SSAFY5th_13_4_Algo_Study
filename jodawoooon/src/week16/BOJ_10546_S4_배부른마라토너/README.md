
## BOJ 10546 S4 배부른마라토너
- silver4
- 자료구조
- HashMap

<br>

### 문제풀이
프로그래머스 Programmers 해시 level1 문제인 '완주하지 못한 선수'랑 같은 문제입니다.  

완주하지 못한 한 사람을 찾기 위해 map을 이용했습니다.  
모든 참가자를 map에 넣습니다.  
이 때 이미 있는 key값이면 value를 증가시키고, 존재 하지 않는 key값이면 value를 1로 합니다.

그리고 완주자에 대해 value를 1씩 줄여줍니다.

그리고 마지막에 map을 검사 했을 때 value가 0이 아니라면 그 key값이 완주하지 못한 선수의 이름이 됩니다.  
<br>

### 결과
메모리 : 31920KB  
시간 : 360ms
 