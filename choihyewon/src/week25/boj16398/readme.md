## BOJ 16398 ํ์ฑ ์ฐ๊ฒฐ 
- Kruskal
- ๐ฅ Gold4
- ๐[ํ์ฑ ์ฐ๊ฒฐ ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://www.acmicpc.net/problem/16398)



## ํ์ด

๋ง์ฐฌ๊ฐ์ง๋ก ํฌ๋ฃจ์ค์นผ ์๊ณ ๋ฆฌ์ฆ์ ์ด์ฉํด์ ํ์์ต๋๋ค. 
i์ j๊ฐ ๊ฐ์ง ์์ ๊ฒฝ์ฐ์๋ง ๊ฐ์ ์ ์ ๋ณด๋ฅผ list์ ๋ด์์ฃผ์๊ณ  ์ด๋ฅผ ๊ฐ์ค์น์์ผ๋ก ์ค๋ฆ์ฐจ์ ์ ๋ ฌ์ ํด์ฃผ์์ต๋๋ค.
๊ทธ๋ฆฌ๊ณ  ์ธ์ดํด์ด ๋ฐ์ํ๋ค๋ฉด ๋ค์์ผ๋ก ๊ฐ์ค์น๊ฐ ๋ฎ์ ๊ฐ์ ์ ์ ํํ์๊ณ  ์ ํ๋ ๊ฐ์ ์ด N-1์ธ ๊ฒฝ์ฐ break ํด์ฃผ์์ต๋๋ค.


## ๋งํ์  

์ฒ์์ ๊ฒฐ๊ณผ์ ํ์์ int๋ก ํด์ฃผ์ด 60%์ฏค์์ ํ๋ ธ์ต๋๋ค๋ก ๊ฒฐ๊ณผ๊ฐ ์ถ๋ ฅ๋์๋๋ฐ long์ผ๋ก ๋ฐ๊พธ์ด ์ฃผ์๋๋ ํด๊ฒฐํ  ์ ์์์ต๋๋ค.

## ์์ค์ฝ๋
~~~java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
import java.util.StringTokenizer;

public class BOJ_16398_G4_ํ์ฑ_์ฐ๊ฒฐ {
	static int N;
	static int[] parents;
	static List<Edge> edgeList = new ArrayList<>();
	static class Edge implements Comparable<Edge>{
		int from;
		int to;
		int weight;
		public Edge(int from, int to, int weight) {
			this.from = from;
			this.to = to;
			this.weight = weight;
		}
		@Override
		public int compareTo(Edge o) {
			// TODO Auto-generated method stub
			return this.weight - o.weight;
		}
	}
	static int find(int a) {
		if(parents[a]==a) {
			return a;
		}
		
		return parents[a] = find(parents[a]);
	}
	static boolean union(int a, int b) {
		int aRoot = find(a);
		int bRoot = find(b);
		
		if(aRoot == bRoot) {
			return false;
		}
		
		parents[bRoot] = aRoot;
		
		return true;
	}
	public static void main(String[] args)throws Exception {
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		N = Integer.parseInt(br.readLine());
		
		parents = new int[N];
		
		for(int i=0; i<N; i++) {
			StringTokenizer st = new StringTokenizer(br.readLine());
			for(int j=0; j<N; j++) {
				int weight = Integer.parseInt(st.nextToken());
				if(i==j)	continue;
				edgeList.add(new Edge(i,j,weight));
			}
		}
		
		for(int i=0; i<N; i++) {
			parents[i] = i;
		}
		
		Collections.sort(edgeList);
		
		long result = 0;
		int count = 0;
		
		for (Edge e : edgeList) {
			if(union(e.from, e.to)){
				result += e.weight;
				
				if(++count == N-1)	break;
			}
		}
		System.out.println(result);

	}

}

~~~

## ๊ฒฐ๊ณผ 

| ๋ฉ๋ชจ๋ฆฌ  | ์๊ฐ |
|----|----|
| 173576kb| 1224ms|
