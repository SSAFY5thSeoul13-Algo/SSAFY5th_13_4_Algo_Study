## BOJ 17086 ์๊ธฐ์์ด2 
- bfs
- ๐ฅ Silver2
- ๐[์๊ธฐ์์ด2 ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://www.acmicpc.net/problem/17086)



## ํ์ด

์ ๋ bfs๋ฅผ ์ด์ฉํ์ฌ ๋ฌธ์ ๋ฅผ ํ์์ต๋๋ค. ๋จผ์  ์๋ ฅ๋ฐ์ ์ซ์๋ฅผ 2์ฐจ์ ๋ฐฐ์ด์ ๋ฃ์ด์ฃผ์์ต๋๋ค.
๊ทธ๋ฆฌ๊ณ  ์์ด๊ฐ ์๋ ์นธ์์ bfs๋ฅผ ์งํํ์์ต๋๋ค.

์ด๋์ 8๋ฐฉํฅ์ด ๊ฐ๋ฅํ๊ธฐ ๋๋ฌธ์ 8๋ฐฉํฅ์ผ๋ก ํ์์ ์งํํ์์ต๋๋ค.
์ด๋์ด ๊ฐ๋ฅํ ๊ฒฝ์ฐ์ ๋ฐฉ๋ฌธ์ฒดํฌ๋ฅผ ํด์ฃผ๊ณ  ๊ฑฐ๋ฆฌ๋ฅผ +1, ์ด๋๊ฐ๋ฅํ ์์น ์ขํ๋ queue์ ๋ฃ์ด์ฃผ์์ต๋๋ค.
๋ง์ฝ ๋ฒ์๋ฅผ ๋ฒ์ด๋๊ฑฐ๋ ๋ฐฉ๋ฌธํ๋ค๋ฉด continue,
์๊ธฐ ์์ด๋ฅผ ๋ง๋ฌ๋ค๋ฉด ํ์ฌ ์ด๋๊ฑฐ๋ฆฌ์ answer์ค ์ต๋๊ฐ ๋น๊ต๋ฅผ ํ์ฌ returnํด์ฃผ์์ต๋๋ค.

~~~java

		Queue<Node> queue = new LinkedList<>();
		boolean[][] visited = new boolean[N][M];
		queue.add(new Node(r,c,cnt));
		visited[r][c] = true;
		
		while(!queue.isEmpty()) {
			Node cur = queue.poll();
			for(int i=0; i<8; i++) {
				int nr = cur.r + dr[i];
				int nc = cur.c + dc[i];
				
				if(nr<0 || nc<0 || nr>=N || nc>=M || visited[nr][nc])	continue;
				
				if(arr[nr][nc]==1) {
					answer = Math.max(answer, cur.cnt+1);
					return;
				}
				
				visited[nr][nc] = true;
				queue.add(new Node(nr,nc,cur.cnt+1));
			}
		}
		
	}
~~~

## ์์ค์ฝ๋
~~~java
import java.io.*;
import java.util.*;

public class BOJ_17086_S2_์๊ธฐ์์ด2 {
	static class Node{
		int r;
		int c;
		int cnt;
		public Node(int r,int c,int cnt) {
			this.r = r;
			this.c = c;
			this.cnt = cnt;
		}
	}
	static int N,M,answer=0;
	static int[][] arr;
	static int[] dr = {-1,-1,-1,0,1,1,1,0};
	static int[] dc = {-1,0,1,1,1,0,-1,-1};
	public static void main(String[] args)throws Exception {
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = new StringTokenizer(br.readLine());
		N = Integer.parseInt(st.nextToken());
		M = Integer.parseInt(st.nextToken());
		
		arr = new int[N][M];
		
		for(int i=0; i<N; i++) {
			st = new StringTokenizer(br.readLine());
			for(int j=0; j<M; j++) {
				arr[i][j] = Integer.parseInt(st.nextToken());
			}
		}
		
		for(int i=0; i<N; i++) {
			for(int j=0; j<M; j++) {
				if(arr[i][j]==0) {
					bfs(i,j,0);
				}
			}
		}
		

		System.out.println(answer);
		
	}
	private static void bfs(int r, int c,int cnt) {
		Queue<Node> queue = new LinkedList<>();
		boolean[][] visited = new boolean[N][M];
		queue.add(new Node(r,c,cnt));
		visited[r][c] = true;
		
		while(!queue.isEmpty()) {
			Node cur = queue.poll();
			for(int i=0; i<8; i++) {
				int nr = cur.r + dr[i];
				int nc = cur.c + dc[i];
				
				if(nr<0 || nc<0 || nr>=N || nc>=M || visited[nr][nc])	continue;
				
				if(arr[nr][nc]==1) {
					answer = Math.max(answer, cur.cnt+1);
					return;
				}
				
				visited[nr][nc] = true;
				queue.add(new Node(nr,nc,cur.cnt+1));
			}
		}
		
	}

}

~~~

## ๊ฒฐ๊ณผ 

| ๋ฉ๋ชจ๋ฆฌ  | ์๊ฐ |
|----|----|
| 169364kb| 376ms|