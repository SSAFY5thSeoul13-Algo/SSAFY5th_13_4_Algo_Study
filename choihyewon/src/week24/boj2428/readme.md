## BOJ 2428 ํ์  
- BinarySearch
- ๐ฅ Silver3 
- ๐[ํ์  ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://www.acmicpc.net/problem/2428)



## ํ์ด

์ฒ์์ ํ์๋ ์ฝ๋๋ ์๊ฐ์ด๊ณผ๊ฐ ๋์์ต๋๋ค. ์ฌ๋ผ์ด๋ฉ ์๋์ฐ๋ก ์ด๋ป๊ฒ ํ์ด์ผํ ์ง ๋ชจ๋ฅด๊ฒ ์ด์,,,

์ผ๋จ ์กฐ๊ฑด์ size(Fi) โค size(Fj) ์ด์๊ธฐ ๋๋ฌธ์ ์ ๋ ฌ์ ํด์ฃผ์๊ณ , ์ด๋ถํ์์ ํตํด size(Fi) โฅ 0.9 ร size(Fj)์ธ ๊ฒฝ์ฐ left๋ฅผ mid+1 ํด์ฃผ์๊ณ , ์๋ ๊ฒฝ์ฐ๋ ํ์ ๋ฒ์๋ฅผ ์ค์ฌ์ฃผ์ด๋ ๋๊ธฐ ๋๋ฌธ์ right๊ฐ์ mid-1๋ก ๋ฐ๊พธ์์ต๋๋ค. 

ํ์์ด ๋๋ ๋ค right๊ฐ์์ i๊ฐ์ ๋นผ์ค๊ฐ์ result์ ๋์ ํด์ฃผ์ด ๋ต์ ๊ตฌํ์์ต๋๋ค. 

## ์์ค์ฝ๋

#### ์๊ฐ์ด๊ณผ ๋์จ ์ฝ๋

~~~java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.Arrays;
import java.util.StringTokenizer;

public class BOJ_2428_S3_ํ์  {

	public static void main(String[] args)throws Exception {
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		int N = Integer.parseInt(br.readLine());
		int result = 0;
		
		int[] files = new int[N];
		

		StringTokenizer st = new StringTokenizer(br.readLine());
		for(int i=0; i<N; i++) {
			files[i] = Integer.parseInt(st.nextToken());
		}
		
		Arrays.sort(files);
		
		for(int i=0; i<N-1; i++) {
			int num1 = files[i];
			for(int j=i+1; j<N; j++) {
				int num2 = files[j];
				
				if(num1>=num2*0.9) {
					result++;
				}else {
					break;
				}
			}
		}
		
		System.out.println(result);
		
		
		
	}

}
~~~


#### ์ ๋ต ์ฝ๋

~~~java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.Arrays;
import java.util.StringTokenizer;

public class BOJ_2428_S3_ํ์  {
	static int N;
	static long result;
	public static void main(String[] args) throws Exception{
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

		N = Integer.parseInt(br.readLine());
		
		StringTokenizer st = new StringTokenizer(br.readLine());
		
		int[] files = new int[N];
	
		for(int i=0; i<N; i++) {
			files[i] = Integer.parseInt(st.nextToken());
		}
		
		// ๋ฐฐ์ด์ ์ค๋ฆ์ฐจ์์ผ๋ก ์ ๋ ฌ 
		Arrays.sort(files);
		
		for(int i=0; i<N; i++) {
			int left = i;
			int right = N-1;
			while(left<=right) {
				int mid = (left+right)/2;
				
				if(files[i]>=files[mid]*0.9) {
					left = mid + 1;
				}else {
					right = mid - 1;
				}
			}
			result += right - i;
		}
		
		
		
		System.out.println(result);
	}
	


}

~~~

## ๊ฒฐ๊ณผ 

| ๋ฉ๋ชจ๋ฆฌ  | ์๊ฐ |
|----|----|
| 33084kb| 424ms|