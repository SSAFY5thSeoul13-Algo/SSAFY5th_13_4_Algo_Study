## BOJ 3190 ๋ฑ 
- Simulation 
- ๐ฅ Gold5
- ๐[๋ฑ ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://www.acmicpc.net/problem/3190)



## ํ์ด

๋จผ์  2์ฐจ์ ๋ฐฐ์ด์ ์ฌ๊ณผ๊ฐ ์์นํ ๊ณณ์ ํ์ํด์ฃผ์์ต๋๋ค.

~~~java
		for(int i=0; i<K; i++) {
			StringTokenizer st = new StringTokenizer(br.readLine());
			int row = Integer.parseInt(st.nextToken());
			int col = Integer.parseInt(st.nextToken());
			// ์ฌ๊ณผ ์๋ ๊ณณ ํ์ 
			arr[row][col] = 1;
		}
~~~

๋ฑ์ ๋ฐฉํฅ ์ ํ ์ ๋ณด๋ฅผ ๋ด๋ ํด๋์ค๋ฅผ ๋ง๋ค์ด ์ฃผ์ด L๊ฐ์ ๋ฐฉํฅ ์ ํ ์ ๋ณด๋ฅผ list์ ๋ด์์ต๋๋ค.

~~~java
	// ๋ฑ์ ๋ฐฉํฅ ์ ํ ์ ๋ณด๋ฅผ ๋ด๋ ํด๋์ค 
	static class DirInfo{
		int sec;
		char dir;
		public DirInfo(int sec,char dir) {
			this.sec = sec;
			this.dir = dir;
		}
	}
~~~

~~~java
		for(int i=0; i<L; i++) {
			StringTokenizer st = new StringTokenizer(br.readLine());
			int sec = Integer.parseInt(st.nextToken());
			char dir = st.nextToken().charAt(0);
			info.add(new DirInfo(sec,dir));
		}
~~~

๋ฑ์ ์ค๋ฅธ์ชฝ ๋ฐฉํฅ์ผ๋ก 1,1 ์ขํ์์ ์์ํ๋ฏ๋ก dr,dc ๊ฐ ํ,์ด ๋ฐฉํฅ์ขํ๋ฅผ ๋ด์ ๋ฐฐ์ด์ ์ฐ ํ ์ข ์ ์์ผ๋ก ๋ฃ์ด์ฃผ์์ต๋๋ค.
๊ทธ๋ฆฌ๊ณ  ํ์ฌ ๋ฑ์ ๋ชธ์ ์์น ์ ๋ณด๋ฅผ ๋ด๋ snake ๋ฆฌ์คํธ์ 1,1์ ๋ฃ์ด์ฃผ์์ต๋๋ค.
๊ทธ ๋ค์ ๋ฑ์ ๋ฐฉํฅ์ ํ์ ๋ณด๋ฅผ ์ด์ฉํ์ฌ ๋ฑ์ ์์ง์ฌ ์ฃผ์์ต๋๋ค. ์ฌ๊ณผ๋ฅผ ๋จน์๋, ๋จน์ง์์๋๋ฅผ ๊ตฌ๋ถํ์ฌ ์์ง์ฌ์ฃผ์์ต๋๋ค.

~~~java
while(true) {
			time++;

			int nextR = curR + dr[curDir];
			int nextC = curC + dc[curDir];
			
			if(isBreak(nextR,nextC))	break;
			
			// ์ฌ๊ณผ๋ฅผ ๋จน๋ ๊ฒฝ์ฐ 
			if(arr[nextR][nextC]==1) {
				snake.add(new int[] {nextR,nextC});
				arr[nextR][nextC] = 0;
			}
			// ์ฌ๊ณผ๊ฐ ์๋ ๊ฒฝ์ฐ 
			else {
				// ๊ผฌ๋ฆฌ๋ฅผ ์ ๊ฑฐํ๋ค.
				snake.remove(0);
				snake.add(new int[] {nextR,nextC});
			}
			
			curR = nextR;
			curC = nextC;
			
			if(idx<L) {
				int infoSec = info.get(idx).sec;
				if(time==infoSec) {
					char changeDir = info.get(idx).dir;
					if(changeDir == 'D') {
						curDir++;
						if(curDir==4) {
							curDir = 0;
						}
					}else if(changeDir == 'L') {
						curDir--;
						if(curDir==-1) {
							curDir = 3;
						}
					}
					idx++;
				}
			}
		}
~~~

๊ทธ๋ฆฌ๊ณ  ๋ฑ์ด ์ ์ฌ๊ฐ ๋ณด๋๋ฅผ ๋๊ฐ๊ฑฐ๋ ์์ ์ ๋ชธ๊ณผ ๋ถ๋ชํ ๊ฒฝ์ฐ breakํด์ฃผ์์ต๋๋ค.(isBreak๋ฉ์๋ ์ด์ฉ)


## ๋งํ์ 
๋ฑ์ด ์ฌ๊ณผ๋ฅผ ๋จน๊ณ ๋ ํ ์ฌ๊ณผ๊ฐ ์์นํ ํ์๋ฅผ ์ง์ฐ๋ ๋ก์ง์ ์ถ๊ฐํด์ฃผ์ด์ผ ํ๋๋ฐ, ์ง๊ธ ํ์ผ์์๋ ๊ทธ ๋ก์ง์ด ์์ด๋ ๋ต์ด ๋์์ด์ ๋ฐ๋ก๋ฅผ ์ฐพ๊ณ ๋ ํ์ ๋ก์ง์ ์ถ๊ฐํ  ์ ์์์ต๋๋ค.

~~~java
				arr[nextR][nextC] = 0;
~~~

## ์์ค์ฝ๋
~~~java
package week27.boj3190;

import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.ArrayList;
import java.util.List;
import java.util.StringTokenizer;

public class BOJ_3190_G5_๋ฑ {
	// ๋ฑ์ ๋ฐฉํฅ ์ ํ ์ ๋ณด๋ฅผ ๋ด๋ ํด๋์ค 
	static class DirInfo{
		int sec;
		char dir;
		public DirInfo(int sec,char dir) {
			this.sec = sec;
			this.dir = dir;
		}
	}
	static int N,K,L;
	static int[][] arr;
	// ์ฐ ํ ์ข ์ ๋ฐฉํฅ 
	static int[] dr = {0,1,0,-1};
	static int[] dc = {1,0,-1,0};
	static List<DirInfo> info = new ArrayList<>();
	// ๋ฑ์ ๋ชธ์ด ์์นํ๊ณ  ์๋ ์ขํ 
	static List<int[]> snake = new ArrayList<>();
	public static void main(String[] args) throws Exception{
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		
		N = Integer.parseInt(br.readLine());
		K = Integer.parseInt(br.readLine());
		
		arr = new int[N+1][N+1];
		
		for(int i=0; i<K; i++) {
			StringTokenizer st = new StringTokenizer(br.readLine());
			int row = Integer.parseInt(st.nextToken());
			int col = Integer.parseInt(st.nextToken());
			// ์ฌ๊ณผ ์๋ ๊ณณ ํ์ 
			arr[row][col] = 1;
		}
		
		L = Integer.parseInt(br.readLine());
		
		for(int i=0; i<L; i++) {
			StringTokenizer st = new StringTokenizer(br.readLine());
			int sec = Integer.parseInt(st.nextToken());
			char dir = st.nextToken().charAt(0);
			info.add(new DirInfo(sec,dir));
		}
		// ๋ฑ์ ์ฒ์์ 1ํ 1์ด์์ ์์ํ๊ณ  ๊ธธ์ด๋ 
		int curR = 1;
		int curC = 1;
		int time = 0;
		int idx = 0;
		int curDir = 0;
		
		snake.add(new int[] {curR,curC});
		
		while(true) {
			time++;

			int nextR = curR + dr[curDir];
			int nextC = curC + dc[curDir];
			
			if(isBreak(nextR,nextC))	break;
			
			// ์ฌ๊ณผ๋ฅผ ๋จน๋ ๊ฒฝ์ฐ 
			if(arr[nextR][nextC]==1) {
				snake.add(new int[] {nextR,nextC});
				arr[nextR][nextC] = 0;
			}
			// ์ฌ๊ณผ๊ฐ ์๋ ๊ฒฝ์ฐ 
			else {
				// ๊ผฌ๋ฆฌ๋ฅผ ์ ๊ฑฐํ๋ค.
				snake.remove(0);
				snake.add(new int[] {nextR,nextC});
			}
			
			curR = nextR;
			curC = nextC;
			
			if(idx<L) {
				int infoSec = info.get(idx).sec;
				if(time==infoSec) {
					char changeDir = info.get(idx).dir;
					if(changeDir == 'D') {
						curDir++;
						if(curDir==4) {
							curDir = 0;
						}
					}else if(changeDir == 'L') {
						curDir--;
						if(curDir==-1) {
							curDir = 3;
						}
					}
					idx++;
				}
			}
		}
		
		System.out.println(time);

	}
	// ๋ฑ์ด ๋ฒฝ์ ๋ถ๋ชํ๊ฑฐ๋ ์์ ์ ๋ชธ์ ๋ถ๋ชํ๋ ๊ฒฝ์ฐ true return
	private static boolean isBreak(int nextR, int nextC) {
		if(nextR<=0 || nextC<=0 || nextR>N || nextC>N)
			return true;
		for(int i=0; i<snake.size(); i++) {
			// ํ์ฌ ๋ฑ์ ๋ชธ์ ์์น 
			int snakeR = snake.get(i)[0];
			int snakeC = snake.get(i)[1];
			if(snakeR == nextR && snakeC == nextC)	return true;
		}
		return false;
	}
	

}

~~~

## ๊ฒฐ๊ณผ 

| ๋ฉ๋ชจ๋ฆฌ  | ์๊ฐ |
|----|----|
| 12016kb| 100ms|