## BOJ 1068 G5 ํธ๋ฆฌ
- ํธ๋ฆฌ
- gold5

<br>


### ๐ ๋ฌธ์  ์ค๋ช
https://www.acmicpc.net/problem/1068

์ฒซ์งธ ์ค์ ํธ๋ฆฌ์ ๋ธ๋์ ๊ฐ์ N์ด ์ฃผ์ด์ง๋ค. N์ 50๋ณด๋ค ์๊ฑฐ๋ ๊ฐ์ ์์ฐ์์ด๋ค. ๋์งธ ์ค์๋ 0๋ฒ ๋ธ๋๋ถํฐ N-1๋ฒ ๋ธ๋๊น์ง, ๊ฐ ๋ธ๋์ ๋ถ๋ชจ๊ฐ ์ฃผ์ด์ง๋ค. ๋ง์ฝ ๋ถ๋ชจ๊ฐ ์๋ค๋ฉด (๋ฃจํธ) -1์ด ์ฃผ์ด์ง๋ค. ์์งธ ์ค์๋ ์ง์ธ ๋ธ๋์ ๋ฒํธ๊ฐ ์ฃผ์ด์ง๋ค.

์ฒซ์งธ ์ค์ ์๋ ฅ์ผ๋ก ์ฃผ์ด์ง ํธ๋ฆฌ์์ ์๋ ฅ์ผ๋ก ์ฃผ์ด์ง ๋ธ๋๋ฅผ ์ง์ ์ ๋, ๋ฆฌํ ๋ธ๋์ ๊ฐ์๋ฅผ ์ถ๋ ฅํ๋ค.

###  ๐ก ํ์ด

๋ณ์
`int N` : ๋ธ๋ ๊ฐ์ 
`int root ` : ๋ฃจํธ ๋ธ๋์ ๋ฒํธ
`int remove` : ์ญ์ ํ  ๋ธ๋์ ๋ฒํธ
`List<Integer>[] tree` : ๊ฐ ํธ๋ฆฌ์ ๋ธ๋์ ํ์ ๋ธ๋ ๋ฒํธ๋ฅผ ์ ์ฅํ  ๋ฆฌ์คํธ


<br>

๊ฐ ๋ฒํธ์ ํด๋นํ๋ ๋ฆฌ์คํธ์ ํ์ ๋ธ๋์ ๋ฒํธ๋ค์ ์ ์ฅํ ํ์ dfs๋ฅผ ํตํด์ ํด๋น ๋ฆฌ์คํธ์ ๊ธธ์ด๊ฐ 0์ด ๋๋ ๊ฒฝ์ฐ๋ฅผ countํ์ฌ ํ์๋ค

๋ฆฌ์คํธ์ ๋ฐฐ์ด์ ๊ฐ๊ฐ ArrayList๋ฅผ ํ ๋นํด์ค๋ค

```java
		for (int i = 0; i < 50; i++) {
			tree[i] = new ArrayList<>();
		}
```

์๋ ฅ์ ๋ฐ์ ๋ ๋ฃจํธ์ ํด๋นํ๋ ๊ฒฝ์ฐ `root`์ ํด๋น ๋ฒํธ๋ฅผ ์ ์ฅํ๊ณ  ์๋ ๊ฒฝ์ฐ๋ ํด๋นํ๋ `tree[]` ๋ฆฌ์คํธ์ ํด๋น ๋ธ๋์ ๋ฒํธ๋ฅผ ์ถ๊ฐํด์ค๋ค 

```java
		//๋ธ๋ ๋ฒํธ
		int idx = 0;
		
		//์๋ ฅ
		while(st.hasMoreTokens()) {
			int num = Integer.parseInt(st.nextToken());
			
			//๋ฃจํธ ๋ธ๋ ๋ฒํธ ์ ์ฅ
			if(num == -1) {
				root = idx;
				idx++;
				
				continue;
			}
			
			//ํด๋น ๋ฒํธ์ ๋ธ๋์ ํ์ ๋ธ๋ ์ ์ฅ
			tree[num].add(idx);
			
			idx++;
		}
```

์ญ์ ํ  ๋ธ๋์ ๋ฒํธ๋ฅผ ์๋ ฅ ๋ฐ๊ณ  `dfs`๋ฅผ ์คํํ๋ค

```java
		//์ญ์ ํ  ๋ธ๋
		remove = Integer.parseInt(br.readLine());
		
		//ํ์
		dfs(root);
```

`dfs` ๋ฉ์๋๋ `tree[num]`์ ์ฌ์ด์ฆ๊ฐ 0์ธ๊ฒฝ์ฐ์ `count`๋ฅผ 1 ์ฆ๊ฐ์ํค๊ณ  ๊ทธ๋ ์ง ์์ ๊ฒฝ์ฐ์๋ ๋ค์ `dfs`๋ฅผ ์คํํ์ฌ ์กด์ฌํ๋ ๋ชจ๋  ๋ธ๋์ ํ์ ๋ธ๋ ๊ฐ์๋ฅผ ํ์ธํ์ฌ ๋ฆฌํ ๋ธ๋์ ์๋ฅผ ๊ณ์ฐํ๋ค

```java
	static void dfs(int num) {
		if(num == remove) {
			return;
		}
		
		int size = tree[num].size();
		
		//์ญ์ ํ ๋ธ๋๊ฐ ํ์์ ์๋ ๊ฒฝ์ฐ
		if(tree[num].contains(remove)) {
			size--;
		}
		
		//ํ์ ๋ธ๋๊ฐ ์์ผ๋ฉด ๋ฆฌํ๋ธ๋
		if(size == 0) {
			count++;
			return;
		}
		
		//๊ณ์ํด์ ํ์ ํ์
		for (Integer idx : tree[num]) {
			if(idx != remove)
				dfs(idx);
		}
	}
```


<br><br>

###  ๐ก ์์ค์ฝ๋
```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.ArrayList;
import java.util.List;
import java.util.StringTokenizer;

public class BOJ_1068_G5_ํธ๋ฆฌ {
	static List<Integer>[] tree = new ArrayList[50];	
	static int N, root, remove, count;
	
	public static void main(String[] args) throws Exception{
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		N = Integer.parseInt(br.readLine());
		
		for (int i = 0; i < 50; i++) {
			tree[i] = new ArrayList<>();
		}
		
		StringTokenizer st = new StringTokenizer(br.readLine());
		
		//๋ธ๋ ๋ฒํธ
		int idx = 0;
		
		//์๋ ฅ
		while(st.hasMoreTokens()) {
			int num = Integer.parseInt(st.nextToken());
			
			//๋ฃจํธ ๋ธ๋ ๋ฒํธ ์ ์ฅ
			if(num == -1) {
				root = idx;
				idx++;
				
				continue;
			}
			
			//ํด๋น ๋ฒํธ์ ๋ธ๋์ ํ์ ๋ธ๋ ์ ์ฅ
			tree[num].add(idx);
			
			idx++;
		}
		
		//์ญ์ ํ  ๋ธ๋
		remove = Integer.parseInt(br.readLine());
		
		//ํ์
		dfs(root);
		
		System.out.println(count);
	}
	
	static void dfs(int num) {
		if(num == remove) {
			return;
		}
		
		int size = tree[num].size();
		
		//์ญ์ ํ ๋ธ๋๊ฐ ํ์์ ์๋ ๊ฒฝ์ฐ
		if(tree[num].contains(remove)) {
			size--;
		}
		
		//ํ์ ๋ธ๋๊ฐ ์์ผ๋ฉด ๋ฆฌํ๋ธ๋
		if(size == 0) {
			count++;
			return;
		}
		
		//๊ณ์ํด์ ํ์ ํ์
		for (Integer idx : tree[num]) {
			if(idx != remove)
				dfs(idx);
		}
	}
}



```


<br>



๋ฉ๋ชจ๋ฆฌ|์๊ฐ
--|--
11604 KB |88 ms