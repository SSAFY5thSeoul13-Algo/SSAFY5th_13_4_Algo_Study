## BOJ 10986 ๋๋จธ์ง ํฉ 
- Prefix Sum, Math 
- ๐ฅ Gold3
- ๐[๋๋จธ์ง ํฉ ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://www.acmicpc.net/problem/10986)



## ํ์ด

์ฒ์์๋ ๊ฐ index๊น์ง์ ๋์ ํฉ์ ๋ฐฐ์ด์ ๋ฃ์ด์ค ๋ค ์ด์คfor๋ฌธ์ผ๋ก ๋ฌธ์ ๋ฅผ ํ์์ผ๋ ์๊ฐ์ด๊ณผ๊ฐ ๋์์ต๋๋ค.

์ฌ๊ธฐ์ M์ผ๋ก ๋๋์ด ๋จ์ด์ง๋ ๊ตฌ๊ฐ์ ๊ตฌํ๊ธฐ ์ํด, (arr[j]-arr[i-1])%M = 0 ์ธ ๊ตฌ๊ฐ์ ์ฐพ์์ผ ํฉ๋๋ค.

(arr[j]-arr[i-1])%M = 0 ๋ ๋ถ๋ฐฐ๋ฒ์น์ ํตํด arr[j]%M-arr[i-1]%M = 0์ผ๋ก ๋ํ๋ผ ์ ์๊ณ  ์ด๋ ๊ณง arr[j]%M = arr[i-1]%M ์ ๋ํ๋๋๋ค. ๋ฐ๋ผ์ ๋์ ํฉ ๋ฐฐ์ด์ค M์ผ๋ก ๋๋์์ ๋ ๋๋จธ์ง๊ฐ ๊ฐ์ ๊ตฌ๊ฐ์ ์ฐพ์ผ๋ฉด ๋ฉ๋๋ค.

~~~Java
		for(int i=0; i<N; i++) {
			sum += Integer.parseInt(st.nextToken())%M;
			arr[sum%M]++;
		}
~~~

๋ฐฐ์ด์๋ ๋์ ํฉ์ ๋๋จธ์ง๋ฅผ ๊ณ์ฐํ์ฌ count ํด์ค๋๋ค.

~~~java
		for(int i=0; i<M; i++) {
			int n = arr[i];
			result += (long) n*(n-1)/2;
		}
~~~

๋ชจ๋  ๋์ ํฉ์ ๋ํ ๋๋จธ์ง๋ฅผ ์ ์ฅํ์์ผ๋ฉด ๋๋จธ์ง๊ฐ ๊ฐ์ ๊ตฌ๊ฐ๋ผ๋ฆฌ์ ๊ฒฝ์ฐ์ ์๋ฅผ ๊ตฌํด์ค๋๋ค.

์ด์ ์ฝ๋๋ณด๋ค ํ์ฌ์ฝ๋๋ฅผ ํตํด ์๊ฐ ๋ณต์ก๋๋ฅผ O(N)์ผ๋ก ์ค์ผ ์ ์์์ต๋๋ค. 

## ์์ค์ฝ๋

#### ์๊ฐ์ด๊ณผ ๋ ์ฝ๋ 
~~~java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

public class BOJ_10986_G3_๋๋จธ์ง_ํฉ {

	public static void main(String[] args)throws Exception {
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = new StringTokenizer(br.readLine());
		
		int N = Integer.parseInt(st.nextToken());
		int M = Integer.parseInt(st.nextToken());
		
		int[] arr = new int[N+1];
		
		
		st = new StringTokenizer(br.readLine());
		for(int i=1; i<=N; i++) {
			arr[i] = arr[i-1] + Integer.parseInt(st.nextToken());
		}
		
		int cnt = 0;
		for(int i=1; i<=N; i++) {
			for(int j=i; j<=N; j++) {
				int sum = arr[j] - arr[i-1];
				if(sum%3==0) {
					cnt++;
				}
			}
		}
		
		System.out.println(cnt);

	}

}
~~~

#### ์ ๋ต์ฝ๋ 

~~~java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

public class BOJ_10986_G3_๋๋จธ์ง_ํฉ {

	public static void main(String[] args)throws Exception {
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st = new StringTokenizer(br.readLine());
		
		int N = Integer.parseInt(st.nextToken());
		int M = Integer.parseInt(st.nextToken());
		
		// ๋๋จธ์ง๋ฅผ ์ ์ฅํ๋ ๋ฐฐ์ด 
		int[] arr = new int[M];
		
		int sum = 0;
		st = new StringTokenizer(br.readLine());
		for(int i=0; i<N; i++) {
			sum += Integer.parseInt(st.nextToken())%M;
			arr[sum%M]++;
		}
		
		long result = arr[0];
		for(int i=0; i<M; i++) {
			int n = arr[i];
			result += (long) n*(n-1)/2;
		}
		
		System.out.println(result);
		

	}

}
~~~

## ๊ฒฐ๊ณผ 

| ๋ฉ๋ชจ๋ฆฌ  | ์๊ฐ |
|----|----|
|160468kb| 440ms|