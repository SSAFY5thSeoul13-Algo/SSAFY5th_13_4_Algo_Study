## BOJ 2075 N๋ฒ์งธ ํฐ ์ 
- PriorityQueue, SlidingWindow
- ๐ฅ Gold4
- ๐[N๋ฒ์งธ ํฐ ์ ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://www.acmicpc.net/problem/2075)



## ํ์ด

์ฌ๋ผ์ด๋ฉ ์๋์ฐ๋ฅผ ์ด์ฉํด์ ๋ฌธ์ ๋ฅผ ํ๊ณ ์ถ์ด์ ๋ค์ ํ์๋๋ฐ, ์ฐ์ ์์ ํ๋ฅผ ์ฌ์ฉํ์ฌ ์ด๊ธฐ์๋ ๊ฐ์ ๋ฃ์ด์ฃผ๊ณ  ํ๋ Nํฌ๊ธฐ๋งํผ ๊ธธ์ด๋ฅผ ๊ณ ์ ํฉ๋๋ค. N๋ฒ์งธ ํฐ์๋ฅผ ๊ตฌํ๋ ๊ฒ์ด๊ธฐ ๋๋ฌธ์ ํ์ ์๋จ์ ์๋ ๊ฐ์ด ๋ค์ด์ค๋ ์ซ์๋ณด๋ค ์๋ค๋ฉด ๊ทธ ๊ฐ์ pollํด์ฃผ๊ณ  ์๋ก์ด ๊ฐ์ ๋ฃ์ด์ค๋๋ค.

์๋ ฅ๋ฐ์ ์ซ์๊ฐ ๋ชจ๋ ๋ค์ด๊ฐ๋ค๋ฉด ์ฐ์ ์์ ํ์์ ์ ์ผ ์๋จ์ ์๋ ๊ฐ์ ์ถ๋ ฅํด์ฃผ๋ฉด N๋ฒ์งธ ํฐ์๋ฅผ ๊ตฌํ  ์ ์์ต๋๋ค.


## ์์ค์ฝ๋
~~~java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.PriorityQueue;
import java.util.StringTokenizer;

public class BOJ_2075_G5_N๋ฒ์งธ_ํฐ_์ {

	public static void main(String[] args)throws Exception {
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		int N = Integer.parseInt(br.readLine());
		
		PriorityQueue<Integer> pq = new PriorityQueue<>();
		
		for(int i=0; i<N; i++) {
			StringTokenizer st = new StringTokenizer(br.readLine());
			for(int j=0; j<N; j++) {
				int num = Integer.parseInt(st.nextToken());
				// ํ์ ๊ธธ์ด๊ฐ N๊ณผ ๊ฐ๋ค๋ฉด 
				if(pq.size()==N) {
					if(pq.peek()<num) {
						pq.poll();
						pq.add(num);
					}
				}else {
					pq.add(num);
				}
				
			}
		}
		
		System.out.println(pq.poll());

	}

}

~~~

## ๊ฒฐ๊ณผ 

| ๋ฉ๋ชจ๋ฆฌ  | ์๊ฐ |
|----|----|
|293420kb| 888ms|