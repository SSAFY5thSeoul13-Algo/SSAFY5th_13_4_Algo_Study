## BOJ 2096 ๋ด๋ ค๊ฐ๊ธฐ 
- Dp 
- ๐ฅ Gold4
- ๐[๋ด๋ ค๊ฐ๊ธฐ ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://www.acmicpc.net/problem/2096)


## ํ์ด

๋จผ์  ์ด๊ธฐ๊ฐ์ ๊ฐ ์๋ ฅ๊ฐ์ผ๋ก ์ค์ ํด์ฃผ์์ต๋๋ค.

๊ทธ๋ฆฌ๊ณ  ๊ฐ ๋ฐฐ์ด์์ ํ์ฌ ์์นํ๊ณ  ์๋ ๊ณณ์์ ๊ฐ ์ ์๋ ๊ณณ์ ์๋ผ๋ฆฌ ์ต๋์ต์ ๋น๊ต๋ฅผ ํ์ฌ ๊ฐ์ ๊ฐฑ์ ํด์ฃผ์์ต๋๋ค.

์๋ฅผ ๋ค์ด ์ต์๊ฐ์ ๊ตฌํ๋ค๊ณ  ํ๋ฉด, 

~~~java
			min[0] = Math.min(min[0], min[1]) + arr[0];
			min[1] = Math.min(Math.min(min[0],min[1]),min[2]) + arr[1];
			min[2] = Math.min(min[1], min[2]) + arr[2];
~~~

๋ด๋ ค๊ฐ ์ ์๋ ๊ฒฝ์ฐ์์ ์ต์๊ฐ์ ์ฐพ์ ๋ด๋ ค๊ฐ ๋ค์ ์์ ๋ํด์ฃผ๋ฉด ๋ฉ๋๋ค.

๊ทธ ํ ๋ฐฐ์ด์ ์ ๋ ฌํ์ฌ ์ต์๊ฐ์ธ ๊ฒฝ์ฐ๋ 0๋ฒ์งธ ๊ฐ์ ์ต๋๊ฐ์ธ ๊ฒฝ์ฐ 2๋ฒ์งธ ๊ฐ์ ์ถ๋ ฅํด์ฃผ์์ต๋๋ค.

## ์์ค์ฝ๋
~~~java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.Arrays;
import java.util.StringTokenizer;

public class BOJ_2096_G4_๋ด๋ ค๊ฐ๊ธฐ {

	public static void main(String[] args)throws Exception {
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		int N = Integer.parseInt(br.readLine());
		
		int[] arr = new int[3];
		int[] min = new int[3];
        int[] max = new int[3];

        for(int i=0; i<N; i++) {
			StringTokenizer st = new StringTokenizer(br.readLine());
			for(int j=0; j<3; j++) {
				arr[j] = Integer.parseInt(st.nextToken());	
			}
			
			// ์ด๊ธฐ๊ฐ ์ค์  
			if(i==0) {
				min[0] = max[0] = arr[0];
				min[1] = max[1] = arr[1];
				min[2] = max[2] = arr[2];
				continue;
			}

			// ๋ฐ๋ก min๋ฐฐ์ด์ ์ต์๊ฐ์ ์ ์ฅํด๋ฒ๋ฆฌ๋ฉด ๋ค์ ๋น๊ตํ ๋ ์ํฅ์ ์ฃผ๋ฏ๋ก ๋ณ์ ์ฌ์ฉ 
			int n1 = Math.min(min[0], min[1]) + arr[0];
			int n2 = Math.min(Math.min(min[0],min[1]),min[2]) + arr[1];
			int n3 = Math.min(min[1], min[2]) + arr[2];
			
			min[0] = n1;
			min[1] = n2;
			min[2] = n3;
			
			// ๋ฐ๋ก max๋ฐฐ์ด์ ์ต๋๊ฐ์ ์ ์ฅํด๋ฒ๋ฆฌ๋ฉด ๋ค์ ๋น๊ตํ ๋ ์ํฅ์ ์ฃผ๋ฏ๋ก ๋ณ์ ์ฌ์ฉ
			int m1 = Math.max(max[0], max[1]) + arr[0];
			int m2 = Math.max(Math.max(max[0],max[1]),max[2]) + arr[1];
			int m3 = Math.max(max[1], max[2]) + arr[2];
			
			max[0] = m1;
			max[1] = m2;
			max[2] = m3;
			
		}
		
        Arrays.sort(min);
        Arrays.sort(max);
        
        System.out.println(max[2] + " " + min[0]);

	}

}

~~~

## ๊ฒฐ๊ณผ 

| ๋ฉ๋ชจ๋ฆฌ  | ์๊ฐ |
|----|----|
| 40824kb| 336ms|