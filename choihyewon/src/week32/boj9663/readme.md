## BOJ 9663 N-Queen
- BackTracking
- ๐ฅ Gold5
- ๐[N-Queen ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://www.acmicpc.net/problem/9663)



## ํ์ด

N- Queen ์ด๋ ์ฒด์คํ ์์ n๊ฐ์ ํธ์ด ์๋ก๋ฅผ ๊ณต๊ฒฉํ  ์ ์๋๋ก ๋ฐฐ์นํ๋ ๊ฒ์ด๋ค.
๊ณต๊ฒฉ์ ํ ์ ์๋๋ก ๋ฐฐ์นํ๊ธฐ ์ํด์๋ ๋์ผํ ํ์ ์์นํ๊ฑฐ๋ ๋๊ฐ์ ์์ ์์นํ๋ฉด ์๋๋ค.
๋ฐ๋ผ์ ๊ฐ ์ด์ ๋ฐ๋ณต๋ฌธ์ ํตํด ์ซ์๋ฅผ ๋์ ์ ์๋ ๋ชจ๋  ๊ฒฝ์ฐ๋ฅผ ๊ตฌํด๋ณธ๋ค.
isPossible ๋ฉ์๋๋ฅผ ํตํด ๊ณต๊ฒฉ์ด ๋ถ๊ฐ๋ฅํ๋ค๋ฉด ๋ค์ ํ์ ๋ค์ด๊ฐ ์ ์๋ ์๋ฅผ ์ฌ๊ท๋ฅผ ํตํด ํ์ํ๋ค.

~~~java

	private static void backTracking(int col) {
		if(col==N) {
			cnt++;
			return;
		}
		
		for(int i=0; i<N; i++) {
			arr[col] = i;
			if(isPossible(col)) {
				backTracking(col+1);
			}
		}
		
		
	}
~~~

isPossible์์๋ ๊ณต๊ฒฉ์ด ๊ฐ๋ฅํ ์์น๊ฐ ์๋๋ผ๋ฉด true๋ฅผ ๊ณต๊ฒฉ์ด ๊ฐ๋ฅํ๋ค๋ฉด false๋ฅผ returnํ๋ค.
๋ง์ฝ i์ ํ๊ณผ ์ ํํ col์ ํ์ด ๊ฐ๋ค๋ฉด ๊ฐ์ ํ์ ์์นํ๋ ๊ฒ์ด๋ฏ๋ก false,
๋๋ ๋ ํธ์ ์ด์ ์ฐจ์ด์ ํ์ ์ฐจ์ด๊ฐ ๊ฐ๋ค๋ฉด ๋๊ฐ์ ์์ ์์นํ๋ ๊ฒ์ด๋ฏ๋ก false๋ฅผ returnํ๋ค.

~~~java
	private static boolean isPossible(int col) {
		for(int i=0; i<col; i++) {
			if(arr[col] == arr[i] || Math.abs(i-col) == Math.abs(arr[i]-arr[col])) {
				return false;
			}
		}
		return true;
	}
~~~

๋ชจ๋  ์ด์ ๋ค ๊ฒ์ฌํ์ผ๋ฉด cnt++์ ํด์ฃผ๊ณ  ๊ฒฐ๊ณผ๋ฅผ ์ถ๋ ฅํ๋ค.




## ์์ค์ฝ๋
~~~java
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class BOJ_9663_G5_N_Queen {
	static int N,cnt;
	static int[] arr;
	public static void main(String[] args) throws Exception {
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		N = Integer.parseInt(br.readLine());

		for(int i=0; i<N; i++) {
			arr = new int[N];
			arr[0] = i;
			backTracking(1);
		}
		
		System.out.println(cnt);
		

	}
	private static void backTracking(int col) {
		if(col==N) {
			cnt++;
			return;
		}
		
		for(int i=0; i<N; i++) {
			arr[col] = i;
			if(isPossible(col)) {
				backTracking(col+1);
			}
		}
		
		
	}
	private static boolean isPossible(int col) {
		for(int i=0; i<col; i++) {
			if(arr[col] == arr[i] || Math.abs(i-col) == Math.abs(arr[i]-arr[col])) {
				return false;
			}
		}
		return true;
	}

}

~~~

## ๊ฒฐ๊ณผ 

| ๋ฉ๋ชจ๋ฆฌ  | ์๊ฐ |
|----|----|
| 12080kb| 5876ms|