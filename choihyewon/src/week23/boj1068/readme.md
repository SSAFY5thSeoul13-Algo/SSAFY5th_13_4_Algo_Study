## BOJ 1068 ํธ๋ฆฌ 
- Tree
- ๐ฅ Gold5
- ๐[ํธ๋ฆฌ ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://www.acmicpc.net/problem/1068)



## ํ์ด

๋จผ์  ๋ธ๋์ ๊ฐ์ N์ ์๋ ฅ๋ฐ๊ณ  ๊ทธ ํฌ๊ธฐ ๋งํผ์ ๋ฐฐ์ด์ ๋ง๋ค์ด ๋๋ฒ์งธ ์ค์ ์๋ ฅ์ ์ฐจ๋ก๋ก ๋ฐ์ ๊ฐ index์ ๋ถ๋ชจ๋ธ๋๋ฒํธ๋ฅผ parent ๋ฐฐ์ด์ ์ ์ฅํฉ๋๋ค.

๊ทธ๋ฆฌ๊ณ  ์ง์ธ ๋ธ๋๋ฅผ ์๋ ฅ๋ฐ๊ณ  ๋ธ๋์ ๊ทธ ์์๋ชจ๋๋ฅผ ๋ชจ๋ ์ง์ฐ๋ ๋ฉ์๋๋ฅผ ์คํํฉ๋๋ค.

~~~java
	private static void delete(int node) {
		// ์ง์์ง ๋ธ๋๋ -2๋ก ํ์ 
		parent[node] = -2;
		for(int i=0; i<N; i++) {
			if(parent[i] == node) {
				delete(i);
			}
		}
		
	}
~~~

์ฌ๊ท๋ฅผ ์ฌ์ฉํ์ฌ ์ง์์ผ ํ๋ ๋ธ๋์ ์์์ด๋ผ๋ฉด ๊ทธ ์์๋ธ๋๋ ์ง์๋๋ค. ์ด๋ ์ง์์ง ๋ธ๋๋ผ๋ ๊ฒ์ ์๊ธฐ ์ํด -2๋ก ํ์ํฉ๋๋ค.


~~~java
	private static void countLeaf(int node) {
		visited[node] = true;
		int childLeaf = 0;
		// root๊ฐ ์ง์์ง ๊ฒฝ์ฐ๋ ์์๋ธ๋๊ฐ 0์ด๋ฏ๋ก ์ง์์ง ๋ธ๋์ธ ๊ฒฝ์ฐ๋ ๋ฉ์๋๋ฅผ ์คํํ์ง ์๋๋ค.
		if(parent[node]!=-2) {
			for(int i=0; i<N; i++) {
				if(!visited[i] && parent[i]==node) {
					childLeaf++;
					countLeaf(i);
				}
			}
			if(childLeaf == 0) {
				answer++;
			}
		}
		
	}
~~~

์ง์ฐ๋ ์์ ํ ๋จ์ ๋ฆฌํ๋ธ๋๋ฅผ ์ธ๋ ๋ฉ์๋๋ฅผ ์คํํฉ๋๋ค. root๋ถํฐ ์ธ๋๋ฐ root๊ฐ ์ง์์ง ๋ธ๋๋ผ๋ฉด ์๋ฌด๊ฒ๋ ํ์ง ์์ต๋๋ค. ๊ฐ ๋ธ๋์ ํ์๋ธ๋๋ฅผ ์ธ ๋ง์ฝ ๋ฆฌํ๋ธ๋๊ฐ 0์ธ๊ฒฝ์ฐ ํด๋น ํธ๋ฆฌ์ ๋ฆฌํ๋ธ๋ ์ด๋ฏ๋ก answer์ countํด์ค๋๋ค. ๊ทธ๋ ๊ฒ ๋ฉ์๋๋ฅผ ์คํํ์ฌ ๊ตฌํ answer๊ฐ ์ด ๋ฆฌํ๋ธ๋์ ๊ฐ์๊ฐ ๋ฉ๋๋ค. 


## ์์ค์ฝ๋
~~~java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

public class BOJ_1068_G5_ํธ๋ฆฌ {
	static int N, deleteNode, answer;
	static int[] parent;
	static boolean[] visited;
	public static void main(String[] args)throws Exception {
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		
		N = Integer.parseInt(br.readLine());
		parent = new int[N];
		visited = new boolean[N];
		
		StringTokenizer st = new StringTokenizer(br.readLine());
		int root = 0;
		for(int i=0; i<N; i++) {
			parent[i] = Integer.parseInt(st.nextToken());
			if(parent[i]==-1) {
				root = i;
			}
		}
		
		deleteNode = Integer.parseInt(br.readLine());

		delete(deleteNode);
		
		int count = 0;
		countLeaf(root);
		
		System.out.println(answer);
		

	}
	// leafNode์ ๊ฐ์๋ฅผ ์ธ์ค๋ค.
	private static void countLeaf(int node) {
		visited[node] = true;
		int childLeaf = 0;
		// root๊ฐ ์ง์์ง ๊ฒฝ์ฐ๋ ์์๋ธ๋๊ฐ 0์ด๋ฏ๋ก ์ง์์ง ๋ธ๋์ธ ๊ฒฝ์ฐ๋ ๋ฉ์๋๋ฅผ ์คํํ์ง ์๋๋ค.
		if(parent[node]!=-2) {
			for(int i=0; i<N; i++) {
				if(!visited[i] && parent[i]==node) {
					childLeaf++;
					countLeaf(i);
				}
			}
			if(childLeaf == 0) {
				answer++;
			}
		}
		
	}
	// ๋ธ๋์ ๊ทธ ์์๋ธ๋๊น์ง ๋ชจ๋ ์ง์ฐ๋ ๋ฉ์๋ 
	private static void delete(int node) {
		// ์ง์์ง ๋ธ๋๋ -2๋ก ํ์ 
		parent[node] = -2;
		for(int i=0; i<N; i++) {
			if(parent[i] == node) {
				delete(i);
			}
		}
		
	}


}

~~~

## ๊ฒฐ๊ณผ 

| ๋ฉ๋ชจ๋ฆฌ  | ์๊ฐ |
|----|----|
|11560kb|88ms|
