## BOJ 17086 S2 ์๊ธฐ ์์ด
- BFS
- silver2

<br>


### ๐ ๋ฌธ์  ์ค๋ช
https://www.acmicpc.net/problem/17086

NรM ํฌ๊ธฐ์ ๊ณต๊ฐ์ ์๊ธฐ ์์ด ์ฌ๋ฌ ๋ง๋ฆฌ๊ฐ ์๋ค. ๊ณต๊ฐ์ 1ร1 ํฌ๊ธฐ์ ์ ์ฌ๊ฐํ ์นธ์ผ๋ก ๋๋์ด์ ธ ์๋ค. ํ ์นธ์๋ ์๊ธฐ ์์ด๊ฐ ์ต๋ 1๋ง๋ฆฌ ์กด์ฌํ๋ค.

์ด๋ค ์นธ์ ์์  ๊ฑฐ๋ฆฌ๋ ๊ทธ ์นธ๊ณผ ๊ฐ์ฅ ๊ฑฐ๋ฆฌ๊ฐ ๊ฐ๊น์ด ์๊ธฐ ์์ด์์ ๊ฑฐ๋ฆฌ์ด๋ค. ๋ ์นธ์ ๊ฑฐ๋ฆฌ๋ ํ๋์ ์นธ์์ ๋ค๋ฅธ ์นธ์ผ๋ก ๊ฐ๊ธฐ ์ํด์ ์ง๋์ผ ํ๋ ์นธ์ ์์ด๊ณ , ์ด๋์ ์ธ์ ํ 8๋ฐฉํฅ(๋๊ฐ์  ํฌํจ)์ด ๊ฐ๋ฅํ๋ค.

์์  ๊ฑฐ๋ฆฌ๊ฐ ๊ฐ์ฅ ํฐ ์นธ์ ๊ตฌํด๋ณด์. 


#### ์๋ ฅ
์ฒซ์งธ ์ค์ ๊ณต๊ฐ์ ํฌ๊ธฐ N๊ณผ M(2 โค N, M โค 50)์ด ์ฃผ์ด์ง๋ค. ๋์งธ ์ค๋ถํฐ N๊ฐ์ ์ค์ ๊ณต๊ฐ์ ์ํ๊ฐ ์ฃผ์ด์ง๋ฉฐ, 0์ ๋น ์นธ, 1์ ์๊ธฐ ์์ด๊ฐ ์๋ ์นธ์ด๋ค. ๋น ์นธ์ ๊ฐ์๊ฐ ํ ๊ฐ ์ด์์ธ ์๋ ฅ๋ง ์ฃผ์ด์ง๋ค.

#### ์ถ๋ ฅ
์ฒซ์งธ ์ค์ ์์  ๊ฑฐ๋ฆฌ์ ์ต๋๊ฐ์ ์ถ๋ ฅํ๋ค.

###  ๐ก ํ์ด

์์ด์ ์์น๋ค์ ๊ธฐ์ค์ผ๋ก bfs๋ฅผ ํ์ฉํด ํ์๋ค.

์์ด์ ์ฒซ ์์น๋ฅผ ๊ธฐ์ค์ผ๋ก 4๋ฐฉํฅ์ ๋ํด์ bfs๋ฅผ ์คํํ๋ฉฐ ๊ฐ ์๊ฐ๋ง๋ค ๋์ฐฉํ๋ ์์น๋ฅผ `tempMap`์ ์ ์ฅํ๋ค.

ํด๋น ์์น์ ๋์ฐฉ์ ํ์ ๋ `tempMap`์ ๊ฐ์ด ์ด์  ์์น์์์ `tempMap`์ ๊ฐ +1 ๋ณด๋ค ํฐ ๊ฒฝ์ฐ์ ํด๋น ์์น์ ๊ฐ์ ๊ฐฑ์ ํ๋ค.

๊ฐ์ ๊ฐฑ์ ํ  ๋ ๋ง๋ค `result`์ ๊ฐฑ์ ํ ๊ฐ์ ์ต๋๊ฐ์ ์ ์ฅํ๊ณ  bfs๊ฐ ๋ชจ๋ ๋๋ ํ์ `result` ๊ฐ์ ์ถ๋ ฅํ๋ค



<br><br>

###  ๐ก ์์ค์ฝ๋
```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.LinkedList;
import java.util.Queue;
import java.util.StringTokenizer;

public class BOJ_17086_S2_์๊ธฐ์์ด2 {
	static int[][] map;
	static int[][] tempMap;
	static int N, M, result;
	static int[][] delta = { { -1, 0 }, { -1, 1 }, { 0, 1 }, { 1, 1 }, { 1, 0 }, { 1, -1 }, { 0, -1 }, { -1, -1 }, };
	static Queue<int[]> q = new LinkedList<>();

	public static void main(String[] args) throws Exception {
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

		StringTokenizer st = new StringTokenizer(br.readLine());

		N = Integer.parseInt(st.nextToken());
		M = Integer.parseInt(st.nextToken());

		map = new int[N][M];
		tempMap = new int[N][M];

		for (int i = 0; i < N; i++) {
			st = new StringTokenizer(br.readLine());
			for (int j = 0; j < M; j++) {
				tempMap[i][j] = Integer.MAX_VALUE;
				map[i][j] = Integer.parseInt(st.nextToken());
				
				if(map[i][j] == 1) {
					q.offer(new int[] { i, j });
					tempMap[i][j] = 0;
				}
			}
		}

		bfs();
		
		for (int i = 0; i < N; i++) {
			for (int j = 0; j < M; j++) {
				result = Math.max(result, tempMap[i][j]);
			}
		}

		System.out.println(result);
	}

	static void bfs() {

		while (!q.isEmpty()) {
			int[] p = q.poll();
			int py = p[0];
			int px = p[1];

			for (int d = 0; d < 8; d++) {
				int ny = py + delta[d][0];
				int nx = px + delta[d][1];

				if ((ny < 0 || nx < 0 || ny >= N || nx >= M) || tempMap[ny][nx] <= tempMap[py][px] +1 )	continue;

				tempMap[ny][nx] = tempMap[py][px] + 1;
				result = Math.max(result, tempMap[ny][nx]);
				q.offer(new int[] { ny, nx });
			}
		}
	}

}





```


<br>



๋ฉ๋ชจ๋ฆฌ|์๊ฐ
--|--
12108 KB|96 ms