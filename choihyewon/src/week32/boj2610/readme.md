## BOJ 2610 νμμ€λΉ 
- Floyd-Warshall
- π₯ Gold2
- π[νμμ€λΉ λ¬Έμ  λ°λ‘κ°κΈ°](https://www.acmicpc.net/problem/2610)



## νμ΄

μ΄ λ¬Έμ λ νλ‘μ΄λμμ¬ μκ³ λ¦¬μ¦μ μ΄μ©νμ¬ λ¨Όμ  κ° λ²νΈμ μκ²¬μ λ¬μκ°μ κ΅¬ν΄μ£Όμμ΅λλ€.

~~~java
		arr = new int[N+1][N+1];
		
		for(int i=1; i<=N; i++) {
			for(int j=1; j<=N; j++) {
				if(i!=j)
					arr[i][j] = INF;
			}
		}
		
		for(int i=0; i<M; i++) {
			StringTokenizer st = new StringTokenizer(br.readLine());
			int tmp1 = Integer.parseInt(st.nextToken());
			int tmp2 = Integer.parseInt(st.nextToken());
			arr[tmp1][tmp2] = 1;
			arr[tmp2][tmp1] = 1;
		}
		
		for(int j=1; j<=N; j++) {
			for(int i=1; i<=N; i++) {
				if(i==j)	continue;
				for(int k=1; k<=N; k++) {
					if(j==k || i==k)	continue;
					if(arr[i][k]>arr[i][j] + arr[j][k]) {
						arr[i][k] = arr[i][j] + arr[j][k];
					}
				}
			}
		}
~~~

μ΄λ κ² κ΅¬ν΄μ§ 2μ°¨μ λ°°μ΄μμ 10001μΈ κ°μ λ€λ₯Έ μμν λ²νΈμ΄λ―λ‘ μ λ¬ν  μ μμ΅λλ€.
λ¨Όμ  κ°μ μμνλ₯Ό κ΅¬νκΈ° μν΄ boolean νμ λ°°μ΄μ ν΅ν΄ 1λ² λΆν° NκΉμ§ κ²μ¬λ₯Ό ν΄μ€λλ€.
κ°μ μμνλ₯Ό κ΅¬νκΈ° μν΄ μκΈ°μμ κ³Ό κ°μ μ«μμ΄λ©΄ continue, 
λ°©λ¬Ένμ§ μμ λ²νΈμ΄κ³  κ·Έ κ°μ΄ INFκ° μλλΌλ©΄ μμ§ μμνμ λ°°μ λμ§ μμ μ λ¬κ°λ₯ν λ²νΈμ΄λ―λ‘ κ°μ μμν λ¦¬μ€νΈμ λ£μ΄μ€λλ€.

~~~java
		List<Integer> commission = new ArrayList<>();
		visited[idx] = true;
		commission.add(idx);
		
		for(int i=1; i<=N; i++) {
			if(i==idx)	continue;
			if(arr[idx][i] != INF && !visited[i]) {
				visited[i] = true;
				commission.add(i);
			}
		}
~~~

κ·Έλ¦¬κ³  κ·Έ μμνμ λνλ₯Ό κ΅¬νκΈ° μν΄ κ° λ²νΈλ€μ μκ²¬μ λ¬μκ°μ μ΅λκ° μ€ μ΅μκ°μ κ΅¬ν΄μ£Όμμ΅λλ€.

~~~java
		int min = INF;
		int leaderNum = 0;
		for(int i=0; i<commission.size(); i++) {
			int tmp = 0;
			int a = commission.get(i);
			for(int j=0; j<commission.size(); j++) {
				if(i==j)	continue;
				int b = commission.get(j);
				if(tmp<arr[a][b]) {
					tmp = arr[a][b];
				}
			}
			if(min>tmp) {
				min = tmp;
				leaderNum = a;
			}
		}
~~~

μ΄ λ‘μ§μμ returnλ λνμ λ²νΈλ₯Ό listμ λ΄μμ μ€λ¦μ°¨μ μ λ ¬νλ€, μ°¨λ‘λ‘ listμ κΈΈμ΄μ μμλλ‘ κ°μ μΆλ ₯ν΄μ£Όμμ΅λλ€.


## λ§νμ  
μμνμμ λͺ¨λ  μ°Έμμλ€μ μμ¬μ λ¬μκ° μ€ μ΅λκ°μ΄ μ΅μκ° λλλ‘ λνλ₯Ό μ νλ νλ‘κ·Έλ¨ -> μ΄ λΆλΆμ μλͺ» μ΄ν΄νμ¬ λ€λ₯Έ λ‘μ§μΌλ‘ νμμμ΅λλ€..

## μμ€μ½λ
~~~java
import java.io.*;
import java.util.*;

public class BOJ_2610_G2_νμμ€λΉ {
	static final int INF = 10001;
	static boolean[] visited;
	static int N,M;
	static int[][] arr;
	public static void main(String[] args)throws Exception {
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		
		N = Integer.parseInt(br.readLine());
		M = Integer.parseInt(br.readLine());
		
		arr = new int[N+1][N+1];
		
		for(int i=1; i<=N; i++) {
			for(int j=1; j<=N; j++) {
				if(i!=j)
					arr[i][j] = INF;
			}
		}
		
		for(int i=0; i<M; i++) {
			StringTokenizer st = new StringTokenizer(br.readLine());
			int tmp1 = Integer.parseInt(st.nextToken());
			int tmp2 = Integer.parseInt(st.nextToken());
			arr[tmp1][tmp2] = 1;
			arr[tmp2][tmp1] = 1;
		}
		
		for(int j=1; j<=N; j++) {
			for(int i=1; i<=N; i++) {
				if(i==j)	continue;
				for(int k=1; k<=N; k++) {
					if(j==k || i==k)	continue;
					if(arr[i][k]>arr[i][j] + arr[j][k]) {
						arr[i][k] = arr[i][j] + arr[j][k];
					}
				}
			}
		}
		
		visited = new boolean[N+1];
		// κ° λνμ λ²νΈλ₯Ό λ΄λ λ¦¬μ€νΈ 
		ArrayList<Integer> list = new ArrayList<>();
		
		for(int i=1; i<=N; i++) {
			if(!visited[i]) {
				int leader = check(i);
				list.add(leader);
			}
		}
		
		Collections.sort(list);
		
		System.out.println(list.size());
		for(int i=0; i<list.size(); i++) {
			System.out.println(list.get(i));
		}

	}
	static int check(int idx) {
		List<Integer> commission = new ArrayList<>();
		visited[idx] = true;
		commission.add(idx);
		
		for(int i=1; i<=N; i++) {
			if(i==idx)	continue;
			if(arr[idx][i] != INF && !visited[i]) {
				visited[i] = true;
				commission.add(i);
			}
		}
		
		
		int min = INF;
		int leaderNum = 0;
		for(int i=0; i<commission.size(); i++) {
			int tmp = 0;
			int a = commission.get(i);
			for(int j=0; j<commission.size(); j++) {
				if(i==j)	continue;
				int b = commission.get(j);
				if(tmp<arr[a][b]) {
					tmp = arr[a][b];
				}
			}
			if(min>tmp) {
				min = tmp;
				leaderNum = a;
			}
		}
		
		return leaderNum;
	}

}

~~~

## κ²°κ³Ό 

| λ©λͺ¨λ¦¬  | μκ° |
|----|----|
| 12880kb| 136ms|