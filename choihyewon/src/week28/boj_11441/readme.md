## BOJ 11441 ํฉ ๊ตฌํ๊ธฐ 
- Prefix Sum 
- ๐ฅ Silver3 
- ๐[ํฉ๊ตฌํ๊ธฐ ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://www.acmicpc.net/problem/11441)



## ํ์ด

์ด ๋ฌธ์ ๋ ๋์ ํฉ์ ๊ธฐ๋ณธ๊ฐ๋์ ๋์ํด๋ณผ ์ ์์์ต๋๋ค.
์ด๊ธฐ์ N๊น์ง ์ฃผ์ด์ง ๊ฐ์ ๋ฐฐ์ด์ ๊ทธ๋๋ก ๋ฃ๊ณ  M๋ฒ๋งํผ ์ฃผ์ด์ง๋ i๋ถํฐ j๋งํผ์ ๋ฐฐ์ด์ ๊ฐ์ ์ผ์ผ์ด ๋ํด ๊ฒฐ๊ณผ๋ฅผ ๊ตฌํ์์ผ๋ ์๊ฐ์ด๊ณผ๊ฐ ๋์์ต๋๋ค.

๋ฐ๋ผ์ ์ด๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํด 

~~~java
		for(int i=1; i<=N; i++) {
			arr[i] = arr[i-1] + Integer.parseInt(st.nextToken());
		}
~~~

๋ฐฐ์ด์ 0๋ถํฐ index๊น์ง์ ๋์ ํฉ์ ๋ฃ์ด์ฃผ์์ต๋๋ค.

๊ทธ๋ฆฌ๊ณ  i,j๋ ์ฃผ์ด์ง๋ ๊ฒฝ์ฐ ๋ฐฐ์ด์ j๋ฒ์งธ์์ ๋ฐฐ์ด์ i-1๋ฒ์งธ ๊ฐ์ ๋นผ์ฃผ์ด ๊ฒฐ๊ณผ๋ฅผ ๊ตฌํ  ์ ์์์ต๋๋ค.

## ์์ค์ฝ๋
~~~java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

public class BOJ_11441_S3_ํฉ_๊ตฌํ๊ธฐ {

	public static void main(String[] args)throws Exception {
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		int N = Integer.parseInt(br.readLine());
		
		int[] arr = new int[N+1];
		
		StringTokenizer st = new StringTokenizer(br.readLine());

		for(int i=1; i<=N; i++) {
			arr[i] = arr[i-1] + Integer.parseInt(st.nextToken());
		}
		
		int M = Integer.parseInt(br.readLine());
		
		
		for(int a=0; a<M; a++) {
			int sum = 0;
			st = new StringTokenizer(br.readLine());
			int i = Integer.parseInt(st.nextToken());
			int j = Integer.parseInt(st.nextToken());
			
			sum = arr[j] - arr[i-1];
			System.out.println(sum);
		}

	}

}

~~~

## ๊ฒฐ๊ณผ 

| ๋ฉ๋ชจ๋ฆฌ  | ์๊ฐ |
|----|----|
| 62760kb| 1824ms|