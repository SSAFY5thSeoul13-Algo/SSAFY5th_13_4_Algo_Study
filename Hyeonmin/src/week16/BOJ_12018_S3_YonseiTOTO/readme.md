### [문제풀이]
두 개의 우선순의 큐를 사용해서 풀었습니다. pq는 해당 과목을 신청한 사람들이 지불하려는 마일리지를 저장하는 큐이고 myPq는 내가 각 수업을 듣기위해 넣어야하는 마일리지를 저장한 큐입니다.

수강 가능 인원이 신청 인원보다 더 큰 경우에는 myPq에 1을 넣고, 그렇지 않은 경우에는 pq에 사람들의 마일리지를 모두 넣고 신청한 사람 중에 수업을 듣지 못하는 수만큼 pq의 값을 삭제합니다. 그러면 성준이를 제외하고 딱맞는 수의 인원이 수강을 하게 되는데 이 때 그 사람들이 지불한 마일리지중 가장 작은 크기의 마일리지를 성준이가 지불하면 수강이 가능하기 때문에 pq에 값을 하나 myPq에 넣습니다.

위 과정을 끝내고 난 후 myPq에서 값을 하나씩 꺼내 그 크기만큼 M을 감소시키며 수강 가능한 과목 수 count를 증가시키고, 더 이상 남은 수업이 없거나 마일리지가 부족하면 count값을 출력합니다.

### [결과]
메모리 : 12128 KB
시간 : 96 ms