## BOJ 16398 G4 νμ± μ°κ²°
- MST
- gold4

<br>


### π λ¬Έμ  μ€λͺ
https://www.acmicpc.net/problem/16398

νμ΅ μ κ΅­μ μ€μ¬μ νμ± Tμ΄λ€. μ κ΅­μ ν©μ  μ€μμ΄λ νμ± Tμμ μ κ΅­μ ν¨κ³Όμ μΌλ‘ ν΅μΉνκΈ° μν΄μ, Nκ°μ νμ± κ°μ νλ‘μ°λ₯Ό μ€μΉνλ €κ³  νλ€.

λ νμ± κ°μ νλ‘μ°λ₯Ό μ€μΉνλ©΄ μ κ΅­μ ν¨μ κ³Ό λ¬΄μ­μ λ€μ ν νμ±μμ λ€λ₯Έ νμ±μΌλ‘ λ¬΄μν  μ μμ λ§νΌ μ§§μ μκ°λ§μ μ΄λν  μ μλ€. νμ§λ§, μΉμμ μ μ§νκΈ° μν΄μ νλ‘μ° λ΄μ μ κ΅­κ΅°μ μ£ΌλμμΌμΌ νλ€.

λͺ¨λ  νμ± κ°μ νλ‘μ°λ₯Ό μ€μΉνκ³  νλ‘μ° λ΄μ μ κ΅­κ΅°μ μ£Όλνλ©΄, μ κ΅­μ μ μ μ΄ μνλκΈ° λλ¬Έμ ν©μ  μ€μμ΄λ μ κ΅­μ λͺ¨λ  νμ±μ μ°κ²°νλ©΄μ νλ‘μ° κ΄λ¦¬ λΉμ©μ μ΅μνμΌλ‘ νλ € νλ€.

Nκ°μ νμ±μ μ μ 1,β¦,NμΌλ‘ νμνκ³ , νμ± iμ νμ± jμ¬μ΄μ νλ‘μ° κ΄λ¦¬λΉμ©μ Cijμ΄λ©°, i = jμΈ κ²½μ° ν­μ 0μ΄λ€.

μ κ΅­μ μ°Έλͺ¨μΈ λΉμ μ μ κ΅­μ ν©μ  μ€μμ΄λ₯Ό λμ μ κ΅­ λ΄ λͺ¨λ  νμ±μ μ°κ²°νκ³ , κ·Έ μ μ§λΉμ©μ μ΅μννμ.  μ΄λ νλ‘μ°μ μ€μΉλΉμ©μ λ¬΄μνκΈ°λ‘ νλ€.


#### μλ ₯
μλ ₯μΌλ‘ μ²« μ€μ νμ±μ μ N (1 β€ N β€ 1000)μ΄ μ£Όμ΄μ§λ€.

λ λ²μ§Έ μ€λΆν° N+1μ€κΉμ§ κ° νμ±κ°μ νλ‘μ° κ΄λ¦¬ λΉμ©μ΄ N x N νλ ¬ (Cij),  (1 β€ i, j β€ N, 1 β€ Cij β€ 100,000,000, Cij = Cji) λ‘ μ£Όμ΄μ§λ€.

#### μΆλ ₯
λͺ¨λ  νμ±μ μ°κ²°νμ λ, μ΅μ νλ‘μ°μ κ΄λ¦¬λΉμ©μ μΆλ ₯νλ€.

###  π‘ νμ΄

kruskal μκ³ λ¦¬μ¦μ μ΄μ©ν΄μ νμλ€

κ° λΈλμ μ΅μμ λΈλλ₯Ό μκΈ° μμ μΌλ‘ μ€μ 

```java
		parent = new int[N];
		
		for (int i = 0; i < N; i++) {
			parent[i] = i;
		}
```

λͺ¨λ  κ°μ μ λν μ λ³΄λ₯Ό `pq`μ μ μ₯. κ°μ μ κ°μ€μΉλ‘ μ€λ¦μ°¨μ μ λ ¬

```java
		for (int i = 0; i < N; i++) {
			StringTokenizer st = new StringTokenizer(br.readLine());
			
			//μκΈ° μμ μ λν κ²½λ‘κ° μλ κ²½μ° pqμ μ μ₯
			for (int j = 0; j < N; j++) {
				int weight = Integer.parseInt(st.nextToken());
				
				if(weight == 0)	continue;
				
				pq.offer(new Edge(i,j,weight));
			}
		}
```

MSTλ₯Ό κ΅¬ν  λ κΉμ§ κ°μ μ μ ν

```java
		while(!pq.isEmpty()) {
			
			//λͺ¨λ  κ²½λ‘κ° μ€μ λ κ²½μ°
			if(count == N-1)
				break;
			
			Edge edge = pq.poll();
			
			//λ λΈλμ μ΅μμ λΆλͺ¨ λΈλ
			int parentOne = findParent(edge.nodeOne);
			int parentTwo = findParent(edge.nodeTwo);
			
			//μν μ§λ¨μ΄ λ€λ₯Έ κ²½μ°
			if(parentOne != parentTwo) {
				result += edge.weight;
				union(parentOne, parentTwo);
				count++;
			}
		}
```

μλ ₯ν λΈλμ μ΅μμ λΆλͺ¨ λΈλλ₯Ό λ¦¬ν΄νλ λ©μλ

```java
	static int findParent(int idx) {
		if(parent[idx] == idx)
			return idx;
		else
			return findParent(parent[idx]);
	}
```

μλ‘ λ€λ₯Έ λ μ§λ¨μ λΈλλ₯Ό ν μ§λ¨μΌλ‘ ν©μΉλ λ©μλ

```java
	static void union(int idx1, int idx2) {
		parent[idx1] = idx2; 
	}
```



<br><br>

###  π‘ μμ€μ½λ
```java
## BOJ 2096 G4 λ΄λ €κ°κΈ°
- μ¬λΌμ΄λ© μλμ°
- DP
- gold4

<br>


### π λ¬Έμ  μ€λͺ
https://www.acmicpc.net/problem/2096

Nμ€μ 0 μ΄μ 9 μ΄νμ μ«μκ° μΈ κ°μ© μ ν μλ€. λ΄λ €κ°κΈ° κ²μμ νκ³  μλλ°, μ΄ κ²μμ μ²« μ€μμ μμν΄μ λ§μ§λ§ μ€μμ λλκ² λλ λμ΄μ΄λ€.

λ¨Όμ  μ²μμ μ ν μλ μΈ κ°μ μ«μ μ€μμ νλλ₯Ό κ³¨λΌμ μμνκ² λλ€. κ·Έλ¦¬κ³  λ€μ μ€λ‘ λ΄λ €κ°λλ°, λ€μ μ€λ‘ λ΄λ €κ° λμλ λ€μκ³Ό κ°μ μ μ½ μ‘°κ±΄μ΄ μλ€. λ°λ‘ μλμ μλ‘ λμ΄κ°κ±°λ, μλλ©΄ λ°λ‘ μλμ μμ λΆμ΄ μλ μλ‘λ§ μ΄λν  μ μλ€λ κ²μ΄λ€.

μ«μνκ° μ£Όμ΄μ Έ μμ λ, μ»μ μ μλ μ΅λ μ μ, μ΅μ μ μλ₯Ό κ΅¬νλ νλ‘κ·Έλ¨μ μμ±νμμ€. μ μλ μλ£‘μ΄κ° μμΉν κ³³μ μμ ν©μ΄λ€.


#### μλ ₯
μ²«μ§Έ μ€μ N(1 β€ N β€ 100,000)μ΄ μ£Όμ΄μ§λ€. λ€μ Nκ°μ μ€μλ μ«μκ° μΈ κ°μ© μ£Όμ΄μ§λ€. μ«μλ 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 μ€μ νλκ° λλ€.

#### μΆλ ₯
μ²«μ§Έ μ€μ μ»μ μ μλ μ΅λ μ μμ μ΅μ μ μλ₯Ό λμ΄μ μΆλ ₯νλ€.

###  π‘ νμ΄

λ³μ
`int[][] map` : μλ ₯λ μ«μλ₯Ό μ μ₯ν  λ°°μ΄
`int[][] maxDp` : μ§λμ€λ©΄μ λ ν° κ°μ κ°μ§ κ²½μ°λ₯Ό μ μ₯νλ λ°°μ΄
`int[][] minDp` : μ§λμ€λ©΄μ λ μμ κ°μ κ°μ§ κ²½μ°λ₯Ό μ μ₯νλ λ°°μ΄


<br>

μ΅μλ¨μμ λ΄λ €μ€λ©΄μ λ ν° κ²½μ°λ₯Ό μ μ₯νλ λ°°μ΄κ³Ό λ μμ κ²½μ°λ₯Ό μ μ₯νλ λ°°μ΄ 2κ°μ λ°°μ΄μ μ¬μ©ν΄ κ°μ κ΅¬νμλ€

κ° μμΉμ μ«μλ₯Ό μ μ₯νκ³  `minDp`μ κ°μ μ΅λκ°μΌλ‘ μ΄κΈ°ννλ€

```java
		for (int i = 0; i < N; i++) {
			StringTokenizer st = new StringTokenizer(br.readLine());
			
			for (int j = 0; j < 3; j++) {
				map[i][j] = Integer.parseInt(st.nextToken());
				minDp[i][j] = Integer.MAX_VALUE;
			}
		}
```

μ΅μλ¨μ dpλ°°μ΄μλ `map`κ³Ό κ°μ μ«μλ₯Ό μ μ₯νλ€

```java
		for (int i = 0; i < 3; i++) {
			maxDp[0][i] = minDp[0][i] = map[0][i];
		}
```

μ΅μλ¨λΆν° λ°μΌλ‘ λ΄λ €κ°λ©΄μ κ° μμΉμ μ¬ μ μλ μ΅λκ°, μ΅μκ°μ μ μ₯νλ€

```java
		for (int i = 0; i < N-1; i++) {
			for (int j = 0; j < 3; j++) {
				//μλμ μλ 3λ°©ν₯μ λν΄μ
				for (int d = 0; d < 3; d++) {
					int ny = i + dy[d];
					int nx = j + dx[d];
					
					//λ²μ λ°μ΄λ©΄ μ€ν΅
					if(!canGo(ny, nx))	continue;
					
					//λ ν° μλ₯Ό ny, nxμμΉμ μ μ₯
					maxDp[ny][nx] = Math.max(maxDp[ny][nx], maxDp[i][j] + map[ny][nx]);
					//λ μμ μλ₯Ό ny, nxμμΉμ μ μ₯
					minDp[ny][nx] = Math.min(minDp[ny][nx], minDp[i][j] + map[ny][nx]);
				}
			}
		}
```



<br><br>

###  π‘ μμ€μ½λ
```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.PriorityQueue;
import java.util.StringTokenizer;

public class BOJ_16398_G4_νμ±μ°κ²° {
	static int N, count;
	static long result;
	static int[] parent;
	static PriorityQueue<Edge> pq = new PriorityQueue<>();
	
	static class Edge implements Comparable<Edge>{
		int nodeOne;
		int nodeTwo;
		int weight;
		
		public Edge(int nodeOne, int nodeTwo, int weight) {
			super();
			this.nodeOne = nodeOne;
			this.nodeTwo = nodeTwo;
			this.weight = weight;
		}

		@Override
		public int compareTo(Edge o) {
			return this.weight - o.weight;
		}
	}

	public static void main(String[] args) throws Exception{
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		
		N = Integer.parseInt(br.readLine());
		
		parent = new int[N];
		
		for (int i = 0; i < N; i++) {
			parent[i] = i;
		}
		
		for (int i = 0; i < N; i++) {
			StringTokenizer st = new StringTokenizer(br.readLine());
			
			//μκΈ° μμ μ λν κ²½λ‘κ° μλ κ²½μ° pqμ μ μ₯
			for (int j = 0; j < N; j++) {
				int weight = Integer.parseInt(st.nextToken());
				
				if(weight == 0)	continue;
				
				pq.offer(new Edge(i,j,weight));
			}
		}
		
		while(!pq.isEmpty()) {
			
			//λͺ¨λ  κ²½λ‘κ° μ€μ λ κ²½μ°
			if(count == N-1)
				break;
			
			Edge edge = pq.poll();
			
			//λ λΈλμ μ΅μμ λΆλͺ¨ λΈλ
			int parentOne = findParent(edge.nodeOne);
			int parentTwo = findParent(edge.nodeTwo);
			
			//μν μ§λ¨μ΄ λ€λ₯Έ κ²½μ°
			if(parentOne != parentTwo) {
				result += edge.weight;
				union(parentOne, parentTwo);
				count++;
			}
		}
		
		System.out.println(result);
	}
	
	//ν΄λΉ λΈλμ μ΅μμ λΆλͺ¨ λΈλλ₯Ό λ¦¬ν΄
	static int findParent(int idx) {
		if(parent[idx] == idx)
			return idx;
		else
			return findParent(parent[idx]);
	}
	
	//λ μ§λ¨μ ν©μΉ¨
	static void union(int idx1, int idx2) {
		parent[idx1] = idx2; 
	}
}




```


<br>



λ©λͺ¨λ¦¬|μκ°
--|--
176524 KB|1644 ms