## Programmers - λ°°λ¬ 
- Dijkstra
- Level 2
- Summer/Winter Coding(~2018) 

π[λ°°λ¬ λ¬Έμ  λ°λ‘κ°κΈ°](https://programmers.co.kr/learn/courses/30/lessons/12978)

## νμ΄

ν μ μ μμ μ΅λ¨κ²½λ‘λ₯Ό κ΅¬νλ λ¬Έμ μ΄κΈ° λλ¬Έμ λ€μ΅μ€νΈλΌ μκ³ λ¦¬μ¦μΌλ‘ νμμ΅λλ€.
κΈ°μ‘΄ λ€μ΅μ€νΈλΌ μκ³ λ¦¬μ¦μ μ μ©ν λ€ dist(μ΅λ¨ κ²½λ‘κ° λ€μ΄μλ λ°°μ΄)μμ Kμ΄νμΈ κ°λ§ count ν΄μ£Όμμ΅λλ€. 


## μμ€μ½λ
~~~java
import java.util.*;

public class PROGRAMMERS_λ°°λ¬ {
	static List<Node>[] list;
    static int[] dist;
    static boolean[] visited;
    static final int INF = 100_000_000;
    static class Node implements Comparable<Node>{
        int end;
        int dis;
        public Node(int end, int dis){
            this.end = end;
            this.dis = dis;
        }
        @Override
        public int compareTo(Node o){
            return this.dis - o.dis;
        }
    }
    public int solution(int N, int[][] road, int K) {
        int answer = 0;
        
        list = new ArrayList[N+1];
        dist = new int[N+1];
        visited = new boolean[N+1];
        
        for(int i=1; i<=N; i++){
            list[i] = new ArrayList<>();
        }
        
        Arrays.fill(dist,INF);
        
        for(int i=0; i<road.length; i++){
            int a = road[i][0];
            int b = road[i][1];
            int c = road[i][2];
            
            // μλ°©ν₯μΌλ‘ ν΅ν κ°λ₯ 
            list[a].add(new Node(b,c));
            list[b].add(new Node(a,c));
        }
        
        dijkstra();
        
        for(int i=1; i<=N; i++){
            if(dist[i]>K)   continue;
            answer++;
        }
        return answer;
    }
    static void dijkstra(){
        PriorityQueue<Node> pq = new PriorityQueue<>();
        // 1λ² λ§μμ μμμ μ΄ μμ΄μ 1λ²λ§μμμ λ°°λ¬ μμ 
        pq.add(new Node(1,0));
        dist[1] = 0;
        
        while(!pq.isEmpty()){
            Node curNode = pq.poll();
            int current = curNode.end;
            if(visited[current])    continue;
            // λ°©λ¬Έμ²λ¦¬
            visited[current] = true;
            
            for(Node node : list[current]){
                if(dist[node.end] >= dist[current] + node.dis){
                    dist[node.end] = dist[current] + node.dis;
                    pq.add(new Node(node.end,dist[node.end]));
                }
            }
        }
    }
	

}
~~~

## κ²°κ³Ό 

| μ νμ±  | νμ€νΈ |
|----|----|
|νμ€νΈ 1 |	ν΅κ³Ό (0.51ms, 70.6MB)|
|νμ€νΈ 2 |	ν΅κ³Ό (0.47ms, 60.2MB)|
|νμ€νΈ 3 |	ν΅κ³Ό (0.51ms, 66.9MB)|
|νμ€νΈ 4 |	ν΅κ³Ό (0.56ms, 58.2MB)|
|νμ€νΈ 5 |	ν΅κ³Ό (0.53ms, 73.4MB)|
|νμ€νΈ 6 |	ν΅κ³Ό (0.51ms, 74.5MB)|
|νμ€νΈ 7 |	ν΅κ³Ό (0.52ms, 73MB)|
|νμ€νΈ 8 |	ν΅κ³Ό (0.48ms, 58.8MB)|
|νμ€νΈ 9 |	ν΅κ³Ό (0.50ms, 59.3MB)|
|νμ€νΈ 10 |	ν΅κ³Ό (0.55ms, 71.6MB)|
|νμ€νΈ 11 |	ν΅κ³Ό (0.53ms, 59.7MB)|
|νμ€νΈ 12 |	ν΅κ³Ό (0.60ms, 60.6MB)|
|νμ€νΈ 13 |	ν΅κ³Ό (0.59ms, 72.1MB)|
|νμ€νΈ 14 |	ν΅κ³Ό (1.58ms, 60.4MB)|
|νμ€νΈ 15 |	ν΅κ³Ό (1.86ms, 61MB)|
|νμ€νΈ 16 |	ν΅κ³Ό (0.68ms, 59.5MB)|
|νμ€νΈ 17 |	ν΅κ³Ό (0.54ms, 69.7MB)|
|νμ€νΈ 18 |	ν΅κ³Ό (1.05ms, 72.1MB)|
|νμ€νΈ 19 |	ν΅κ³Ό (1.98ms, 77MB)|
|νμ€νΈ 20 |	ν΅κ³Ό (1.09ms, 71.5MB)|
|νμ€νΈ 21 |	ν΅κ³Ό (2.07ms, 59.9MB)|
|νμ€νΈ 22 |	ν΅κ³Ό (1.31ms, 72.3MB)|
|νμ€νΈ 23 |	ν΅κ³Ό (2.16ms, 72.2MB)|
|νμ€νΈ 24 |	ν΅κ³Ό (1.60ms, 60.4MB)|
|νμ€νΈ 25 |	ν΅κ³Ό (2.09ms, 61MB)|
|νμ€νΈ 26 |	ν΅κ³Ό (3.11ms, 62.7MB)|
|νμ€νΈ 27 |	ν΅κ³Ό (2.10ms, 74.7MB)|
|νμ€νΈ 28 |	ν΅κ³Ό (2.26ms, 77MB)|
|νμ€νΈ 29 |	ν΅κ³Ό (2.55ms, 73.2MB)|
|νμ€νΈ 30 |	ν΅κ³Ό (2.62ms, 74.1MB)|
|νμ€νΈ 31 |	ν΅κ³Ό (0.72ms, 73.5MB)|
|νμ€νΈ 32 |	ν΅κ³Ό (0.71ms, 59.4MB)|
