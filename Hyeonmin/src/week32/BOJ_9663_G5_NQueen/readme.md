## BOJ 9663 G5 N-Queen
- ๋ฐฑํธ๋ํน
- gold5

<br>


### ๐ ๋ฌธ์  ์ค๋ช
https://www.acmicpc.net/problem/9663

N-Queen ๋ฌธ์ ๋ ํฌ๊ธฐ๊ฐ N ร N์ธ ์ฒด์คํ ์์ ํธ N๊ฐ๋ฅผ ์๋ก ๊ณต๊ฒฉํ  ์ ์๊ฒ ๋๋ ๋ฌธ์ ์ด๋ค.

N์ด ์ฃผ์ด์ก์ ๋, ํธ์ ๋๋ ๋ฐฉ๋ฒ์ ์๋ฅผ ๊ตฌํ๋ ํ๋ก๊ทธ๋จ์ ์์ฑํ์์ค.


#### ์๋ ฅ
์ฒซ์งธ ์ค์ N์ด ์ฃผ์ด์ง๋ค. (1 โค N < 15)

#### ์ถ๋ ฅ
์ฒซ์งธ ์ค์ ํธ N๊ฐ๋ฅผ ์๋ก ๊ณต๊ฒฉํ  ์ ์๊ฒ ๋๋ ๊ฒฝ์ฐ์ ์๋ฅผ ์ถ๋ ฅํ๋ค.

###  ๐ก ํ์ด

๊ฐ ํ์ ํ๋์ ํธ ๋ง ๋์ ์ ์๊ณ  ๋ชจ๋  ํ์ ํธ์ด ์๋ ๊ฒฝ์ฐ์๋ง ํธ์ ์๊ฐ `N`์ด ๋๋ค

1ํ๋ถํฐ Nํ๊น์ง ์์๋๋ก ํธ์ ๋์ ๊ฒ์ด๊ธฐ ๋๋ฌธ์ ํธ์ ๋์ ๊ฒฝ์ฐ ๊ทธ ํธ์ผ๋ก ์ธํด ํธ์ ๋ชป๋๊ฒ ๋๋ ์๋ฆฌ๋ ๊ทธ ํ ๊ธฐ์ค์ผ๋ก ๊ฐ๊ฑฐ๋ ๋ฐ์ธ ํ๋ง ๊ณ ๋ คํ๋ฉด ๋๋ค

`map`๋ฐฐ์ด์ ํธ์ ๋๊ฑฐ๋ ๋์ ํธ์ผ๋ก ์ธํด์ ์ ํธ์ ๋ชป๋๋ ๊ฒฝ์ฐ +1์ ํ์ฌ ์ฒดํฌํ๋ค

dfs๋ฐฉ์์ผ๋ก ์ ๋ฐฉ๋ฒ์ ๋ฐ๋ณตํ์ฌ ๋ง์ง๋ง ํ๊น์ง ์คํ์ด ์๋ฃ๋ ๊ฒฝ์ฐ๋ฅผ ๊ตฌํด์ ๋ต์ ๊ตฌํ๋ค



<br><br>

###  ๐ก ์์ค์ฝ๋
```java
package week32.BOJ_9663_G5_NQueen;

import java.io.BufferedReader;
import java.io.InputStreamReader;

public class BOJ_9663_G5_NQueen {
	static int[][] map;
	static boolean[][] isVisited;
	static int N, result;
	static int[][] delta= {
			{1,0},
			{1,-1},
			{1,1},
	};

	public static void main(String[] args) throws Exception{
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		
		N = Integer.parseInt(br.readLine());
		
		map = new int[N][N];
		isVisited = new boolean[N][N];
		
		dfs(0, 0);
		
		System.out.println(result);
	}
	
	static void dfs(int y, int count) {
		if(y == N) {
			if(N == count)	result++;
			return;
		}
		
		for (int j = 0; j < N; j++) {
			if(map[y][j] == 0) {
				inputVisit(y, j);
				dfs(y+1, count+1);
				deleteVisit(y, j);
			}
		}
	}
	
	static void inputVisit(int y, int x) {
		map[y][x]++;
		
		for (int d = 0; d < 3; d++) {
			int ny = y + delta[d][0];
			int nx = x + delta[d][1];
			
			while(isIn(ny, nx)) {
				map[ny][nx]++;
				
				ny += delta[d][0];
				nx += delta[d][1];
			}
		}
	}
	
	static void deleteVisit(int y, int x) {
		map[y][x]--;
		
		for (int d = 0; d < 3; d++) {
			int ny = y + delta[d][0];
			int nx = x + delta[d][1];
			
			while(isIn(ny, nx)) {
				map[ny][nx]--;
				
				ny += delta[d][0];
				nx += delta[d][1];
			}
		}
	}
	
	static boolean isIn(int y, int x) {
		if(y < 0 || x < 0 || y >= N || x >= N)	return false;
		
		return true;
	}

}





```


<br>



๋ฉ๋ชจ๋ฆฌ|์๊ฐ
--|--
14536 KB|2696 ms