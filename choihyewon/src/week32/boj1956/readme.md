## BOJ 1956 ์ด๋ 
- Floyd-Warshall
- ๐ฅ Gold4
- ๐[์ด๋ ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://www.acmicpc.net/problem/1956)



## ํ์ด

์ด ๋ฌธ์ ๋ ๋ชจ๋  ์ ์ ์ผ๋ก๋ถํฐ ๋ชจ๋  ์ ์ ๊น์ง์ ์ต์๊ฑฐ๋ฆฌ๋ฅผ ๊ตฌํ๋ ๋ฌธ์ ์ด๋ฏ๋ก ํ๋ก์ด๋ ์์ฌ ์๊ณ ๋ฆฌ์ฆ์ ์ด์ฉํ์ฌ ํ์์ต๋๋ค.

๋จผ์  2์ฐจ์ ๋ฐฐ์ด์ ์ต๋๊ฐ์ ๋ฃ์ด์ฃผ๊ณ  ์์์ ๊ณผ ๋์ฐฉ์ ์ ๊ธธ์ด ์ ๋ณด๋ฅผ ๋ฃ์ด์ค๋๋ค.

~~~java
		for(int i=1; i<=V; i++) {
			for(int j=1; j<=V; j++) {
				if(i != j)	matrix[i][j] = INF;
			}
		}
		
		for(int i=0; i<E; i++) {
			st = new StringTokenizer(br.readLine());
			int start = Integer.parseInt(st.nextToken());
			int end = Integer.parseInt(st.nextToken());
			int len = Integer.parseInt(st.nextToken());
			
			matrix[start][end] = len;
		}
~~~

๊ทธ๋ฆฌ๊ณ  ํ๋ก์ด๋ ์์ฌ์ ์ด์ฉํ์ฌ ๊ฐ ์ ์ ์ผ๋ก๋ถํฐ ์ ์ ๊น์ง์ ์ต์๊ฑฐ๋ฆฌ๋ฅผ ๊ตฌํด์ค๋๋ค.
์ด ๋, ์ถ๋ฐ์ง๋ก๋ถํฐ ๋์ฐฉ์ง์ ์ต์๊ฑฐ๋ฆฌ๋ฅผ ๊ตฌํ๊ธฐ ์ํด ์ถ๋ฐ์ง-๊ฒฝ์ ์ง + ๊ฒฝ์ ์ง-๋์ฐฉ์ง ์ ํฉ๊ณผ ๋น๊ตํ์ฌ ์ต์๊ฐ์ ๊ฐฑ์ ํฉ๋๋ค.

~~~java
		for(int j=1; j<=V; j++) {
			for(int i=1; i<=V; i++) {
				// ๊ฒฝ์ ์ง์ ์ถ๋ฐ์ง๊ฐ ๊ฐ์ผ๋ฉด continue 
				if(j==i)	continue;
				for(int k=1; k<=V; k++) {
					if(j==k || i==k)	continue;
					// ์ถ๋ฐ์ง - ๋์ฐฉ์ง ๊ฑฐ๋ฆฌ์ ์ถ๋ฐ์ง - ๊ฒฝ์ ์ง - ๋์ฐฉ์ง ๊ฑฐ๋ฆฌ๋ฅผ ๋น๊ตํ์ฌ ์ต์๊ฐ์ผ๋ก ๊ฐฑ์  
					if(matrix[i][k] > matrix[i][j] + matrix[j][k]) {
						matrix[i][k] = matrix[i][j] + matrix[j][k];
						//System.out.println("hgg" + matrix[i][k] + " " +  matrix[i][j] + " " +  matrix[j][k]);
					}
				}

			}
		}
~~~

์ด ๋ฌธ์ ์์๋ ์ต์๊ฑฐ๋ฆฌ๋ฅผ ๊ตฌํ๋ฉด ๋๋๋๊ฒ์ด ์๋๋ผ ์๋ณต์ต์๊ฑฐ๋ฆฌ๋ฅผ ๊ตฌํ๋ ๊ฒ์ด๊ธฐ ๋๋ฌธ์ 
๋ฐฐ์ด์์ ์ถ๋ฐ์ง์ค ๋์ฐฉ์ง๊ฐ ๊ฐ์ ๊ฒฝ์ฐ์ ์ต์๊ฑฐ๋ฆฌ๊ฐ ๊ฐฑ์ ๋์ง ์์ ๊ฒฝ์ฐ๋ฅผ ์ ์ธํ ๊ฑฐ๋ฆฌ์ค ์ ์ผ ์ต์๊ฐ์ ๊ตฌํ์ฌ ๋ต์ ๊ตฌํ์ต๋๋ค.

~~~java
		for(int i=1; i<=V; i++) {
			for(int j=1; j<=V; j++) {
				if(i==j)	continue;
				if(matrix[i][j]!=INF && matrix[j][i]!=INF) {
					int sum = matrix[i][j] + matrix[j][i];
					answer = Math.min(answer, sum);
				}
			}
		}
~~~


## ์์ค์ฝ๋
~~~java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

public class BOJ_1956_G4_์ด๋ {
	static final int INF = 9999999;
	public static void main(String[] args)throws Exception {
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = new StringTokenizer(br.readLine());
		
		int V = Integer.parseInt(st.nextToken());
		int E = Integer.parseInt(st.nextToken());
		
		int[][] matrix = new int[V+1][V+1];
		
		for(int i=1; i<=V; i++) {
			for(int j=1; j<=V; j++) {
				if(i != j)	matrix[i][j] = INF;
			}
		}
		
		for(int i=0; i<E; i++) {
			st = new StringTokenizer(br.readLine());
			int start = Integer.parseInt(st.nextToken());
			int end = Integer.parseInt(st.nextToken());
			int len = Integer.parseInt(st.nextToken());
			
			matrix[start][end] = len;
		}
		
		
		for(int j=1; j<=V; j++) {
			for(int i=1; i<=V; i++) {
				// ๊ฒฝ์ ์ง์ ์ถ๋ฐ์ง๊ฐ ๊ฐ์ผ๋ฉด continue 
				if(j==i)	continue;
				for(int k=1; k<=V; k++) {
					if(j==k || i==k)	continue;
					// ์ถ๋ฐ์ง - ๋์ฐฉ์ง ๊ฑฐ๋ฆฌ์ ์ถ๋ฐ์ง - ๊ฒฝ์ ์ง - ๋์ฐฉ์ง ๊ฑฐ๋ฆฌ๋ฅผ ๋น๊ตํ์ฌ ์ต์๊ฐ์ผ๋ก ๊ฐฑ์  
					if(matrix[i][k] > matrix[i][j] + matrix[j][k]) {
						matrix[i][k] = matrix[i][j] + matrix[j][k];
						//System.out.println("hgg" + matrix[i][k] + " " +  matrix[i][j] + " " +  matrix[j][k]);
					}
				}

			}
		}
		
	
		
		int answer = Integer.MAX_VALUE;
		
		for(int i=1; i<=V; i++) {
			for(int j=1; j<=V; j++) {
				if(i==j)	continue;
				if(matrix[i][j]!=INF && matrix[j][i]!=INF) {
					int sum = matrix[i][j] + matrix[j][i];
					answer = Math.min(answer, sum);
				}
			}
		}
		
		if(answer != Integer.MAX_VALUE) {
			System.out.println(answer);
		}else {
			System.out.println(-1);
		}
		

	}

}

~~~

## ๊ฒฐ๊ณผ 

| ๋ฉ๋ชจ๋ฆฌ  | ์๊ฐ |
|----|----|
| 65288kb| 1176ms|