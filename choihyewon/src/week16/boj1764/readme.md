먼저 듣도 못한 사람을 HashSet에 넣어주고 보도 못한 사람을 입력받을때 듣도 못한 사람의 HashSet에 포함이 된다면, result 리스트에 넣어주어 결과값을 출력해주었습니다. <br>
[막힌점] 처음에 듣도 못한 사람을 ArrayList에 넣어주었는데 시간초과가 나왔습니다. 구글링 결과, ArrayList는 순서도 같이 관리하고 HashSet은 순서를 보장하지 않아 시간 차이가 난다고 하여 HashSet을 사용하였습니다. <br>
메모리 - 26668kb	시간 - 344ms