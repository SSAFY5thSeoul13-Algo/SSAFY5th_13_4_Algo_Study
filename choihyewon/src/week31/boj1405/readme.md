## BOJ 1405 ๋ฏธ์น๋ก๋ด 
- BackTracking 
- ๐ฅ Gold5
- ๐[๋ฏธ์น๋ก๋ด ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://www.acmicpc.net/problem/1405)



## ํ์ด

๊ฐ ๋ฐฉํฅ์ผ๋ก ์ด๋ํ  ํ๋ฅ  -> ์ฒ์์ ๋์๋ฆฟ์๋ก ์๋ ฅ๋ฐ์ผ๋ฏ๋ก /100 ๋๋ * 0.01 ์ ํด์ฃผ์ด์ผํ๋ค.

~~~java
		for(int i=0; i<4; i++) {
			direction[i] = Double.parseDouble(st.nextToken()) / 100;
		}
~~~


N์ด 14๋ณด๋ค ํฌ๋ฉด ์๋๋ฏ๋ก map ํฌ๊ธฐ๋ฅผ 30์ผ๋ก ์ก์์ฃผ์๊ณ  ์์์ ์ 15,15๋ก ๊ณ ์ ์์ผ์ฃผ์๋ค.

~~~java
		visited[15][15] = true;		
		backTracking(15,15,1.0,0);
~~~

๊ทธ๋ฆฌ๊ณ  ๋ฐฑํธ๋ํน์ ํตํด N๋ฒ์ count๊ฐ ์๋ฃ๋๋ฉด(๊ธฐ์ ์กฐ๊ฑด) ํ๋ฅ ์ ๋์ ์ผ๋ก ๋ํด์ฃผ์๋ค. 
์ด ๋ ํ๋ฅ ์ ๊ตฌํ๋ ๋ฐฉ๋ฒ์ ์๋ฅผ ๋ค์ด ํ์ฌ ํ๋ฅ ์ด 1, ๋์ชฝ์ผ๋ก ์ด๋ํ  ํ๋ฅ ์ด 0.25๋ผ๋ฉด ๋์ ๊ณฑํด์ฃผ๋ฉด ๋๋ค.

~~~java
		if(cnt == N) {
			answer += result;
			return;
		}
		
		for(int i=0; i<4; i++) {
			int nr = r + dr[i];
			int nc = c + dc[i];
			
			if(nr<0 || nc<0 || nr>=30 || nc>=30)	continue;

			if(!visited[nr][nc] && direction[i]>0) {
				visited[nr][nc] = true;
				backTracking(nr,nc,result*direction[i],cnt+1);
				visited[nr][nc] = false;
			}

		}
		
	}
~~~



## ์์ค์ฝ๋
~~~java
import java.io.*;
import java.util.*;

public class BOJ_1405_G5_๋ฏธ์น๋ก๋ด {
	// ๋ ์ ๋จ ๋ถ 
	static int[] dr = {0,0,1,-1};
	static int[] dc = {1,-1,0,0};
	static double[] direction = new double[4];
	static boolean[][] visited = new boolean[30][30];
	static int N;
	static double answer;
	public static void main(String[] args) throws Exception{
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = new StringTokenizer(br.readLine());
		
		N = Integer.parseInt(st.nextToken());
		
		for(int i=0; i<4; i++) {
			direction[i] = Double.parseDouble(st.nextToken()) / 100;
		}
		
		// ์์์ ์ (15,15)๋ก ๊ณ ์  
		visited[15][15] = true;
		
		backTracking(15,15,1.0,0);
		
		System.out.println(answer);
		
		
	}
	private static void backTracking(int r, int c, double result, int cnt) {
		if(cnt == N) {
			answer += result;
			return;
		}
		
		for(int i=0; i<4; i++) {
			int nr = r + dr[i];
			int nc = c + dc[i];
			
			if(nr<0 || nc<0 || nr>=30 || nc>=30)	continue;

			if(!visited[nr][nc] && direction[i]>0) {
				visited[nr][nc] = true;
				backTracking(nr,nc,result*direction[i],cnt+1);
				visited[nr][nc] = false;
			}

		}
		
	}

}

~~~

## ๊ฒฐ๊ณผ 

| ๋ฉ๋ชจ๋ฆฌ  | ์๊ฐ |
|----|----|
| 12504kb| 136ms|