## BOJ 1068 G5 ํธ๋ฆฌ
- ํธ๋ฆฌ
- gold5



<br><br>


### ๐ ๋ฌธ์  ์ค๋ช
https://www.acmicpc.net/problem/1068

ํธ๋ฆฌ์์ ๋ฆฌํ ๋ธ๋๋, ์์์ ๊ฐ์๊ฐ 0์ธ ๋ธ๋๋ฅผ ๋งํ๋ค.

ํธ๋ฆฌ๊ฐ ์ฃผ์ด์ก์ ๋, ๋ธ๋ ํ๋๋ฅผ ์ง์ธ ๊ฒ์ด๋ค. ๊ทธ ๋, ๋จ์ ํธ๋ฆฌ์์ ๋ฆฌํ ๋ธ๋์ ๊ฐ์๋ฅผ ๊ตฌํ๋ ํ๋ก๊ทธ๋จ์ ์์ฑํ์์ค. ๋ธ๋๋ฅผ ์ง์ฐ๋ฉด ๊ทธ ๋ธ๋์ ๋ธ๋์ ๋ชจ๋  ์์์ด ํธ๋ฆฌ์์ ์ ๊ฑฐ๋๋ค.

์๋ฅผ ๋ค์ด, ๋ค์๊ณผ ๊ฐ์ ํธ๋ฆฌ๊ฐ ์๋ค๊ณ  ํ์.

![](https://images.velog.io/images/jodawooooon/post/556fb903-84e5-4ef1-801e-a7ea0d9f6ed0/image.png)

ํ์ฌ ๋ฆฌํ ๋ธ๋์ ๊ฐ์๋ 3๊ฐ์ด๋ค. (์ด๋ก์ ์์น ๋ ๋ธ๋) ์ด๋, 1๋ฒ์ ์ง์ฐ๋ฉด, ๋ค์๊ณผ ๊ฐ์ด ๋ณํ๋ค. ๊ฒ์ ์์ผ๋ก ์์น ๋ ๋ธ๋๊ฐ ํธ๋ฆฌ์์ ์ ๊ฑฐ๋ ๋ธ๋์ด๋ค.

![](https://images.velog.io/images/jodawooooon/post/88067632-22c2-4cbf-94f3-80f049e49ea1/image.png)

์ด์  ๋ฆฌํ ๋ธ๋์ ๊ฐ์๋ 1๊ฐ์ด๋ค.

<br>

#### โ ์๋ ฅ
์ฒซ์งธ ์ค์ ํธ๋ฆฌ์ ๋ธ๋์ ๊ฐ์ N์ด ์ฃผ์ด์ง๋ค. N์ 50๋ณด๋ค ์๊ฑฐ๋ ๊ฐ์ ์์ฐ์์ด๋ค. ๋์งธ ์ค์๋ 0๋ฒ ๋ธ๋๋ถํฐ N-1๋ฒ ๋ธ๋๊น์ง, ๊ฐ ๋ธ๋์ ๋ถ๋ชจ๊ฐ ์ฃผ์ด์ง๋ค. ๋ง์ฝ ๋ถ๋ชจ๊ฐ ์๋ค๋ฉด (๋ฃจํธ) -1์ด ์ฃผ์ด์ง๋ค. ์์งธ ์ค์๋ ์ง์ธ ๋ธ๋์ ๋ฒํธ๊ฐ ์ฃผ์ด์ง๋ค.
<br>

#### โ ์ถ๋ ฅ
์ฒซ์งธ ์ค์ ์๋ ฅ์ผ๋ก ์ฃผ์ด์ง ํธ๋ฆฌ์์ ์๋ ฅ์ผ๋ก ์ฃผ์ด์ง ๋ธ๋๋ฅผ ์ง์ ์ ๋, ๋ฆฌํ ๋ธ๋์ ๊ฐ์๋ฅผ ์ถ๋ ฅํ๋ค.
<br>


<br><br>

###  ๐ก ํ์ด


- `ArrayList<Integer>[] tree` : tree ์ ๋ณด๋ฅผ ์ ์ฅํ  ์๋ฃ๊ตฌ์กฐ
- `root` : root ๋ธ๋ ๋ฒํธ๋ฅผ ์ ์ฅํ  ๋ณ์
- `tgt` : ์ญ์ ํ  ๋ธ๋ ๋ฒํธ
- `dfs` : ๋ฆฌํ ๋ธ๋ ํ์

์๋ ฅ๋ฐ์ ์ ๋ณด๋ฅผ ๋ฐํ์ผ๋ก tree๋ฅผ ์ธํํ๊ณ , root ๋ธ๋๋ฅผ ์ค์ ํ๋ค.
```java
		for(int i=0; i<N ; i++) {
			int parent = Integer.parseInt(st.nextToken()); //๊ฐ ๋ธ๋์ ๋ถ๋ชจ
			
			if(parent==-1) root = i; //๋ถ๋ชจ๊ฐ ์๋ค๋ฉด -1์ด ์ฃผ์ด์ง๋ค. ์ฆ ๋ฃจํธ์ด๋ค.
			else tree[parent].add(i);
		}
```
๊ทธ๋ฆฌ๊ณ  root๋ถํฐ `dfs`๋ฅผ ์ด์ฉํ์ฌ ๋ฆฌํ๋ธ๋๋ฅผ ํ์ํ๋ค.  

<br>

dfs ๋ฉ์๋ ๋ด์ ๊ตฌ์กฐ๋ ๋ค์๊ณผ ๊ฐ๋ค.

1. ํด๋น ๋ธ๋๊ฐ `tgt`์ด๋ฉด (์ญ์ ํ  ๋ธ๋์ด๋ฉด) ํ์์ ๋ฉ์ถ๋ค.
```java
		if(node==tgt) return; //์ญ์ ํ  ๋ธ๋์ด๋ฉด ํ์ ์ค์ง
```

2. ํด๋น ๋ธ๋๊ฐ ์์์ด ์๋ค๋ฉด ๋ฆฌํ๋ธ๋์ด๋ค.
	๋ฐ๋ผ์ `ans++`ํ๊ณ  ํ์์ ๋ฉ์ถ๋ค.
```java
		if(tree[node].size()==0) {
			//์์์ด ์๋ค => ๋ฆฌํ๋ธ๋์ด๋ค.
			ans++;
			return;
		}
```
3. ํด๋น ๋ธ๋์ ์์๋ธ๋๋ฅผ ๊ณ์ ํ์ํ๋ค.
	์ด ๋, ํ์ฌ ๋ธ๋๊ฐ ์ค์ง `tgt`๋ธ๋๋ง์ ์์๋ธ๋๋ก ๊ฐ์ง๊ณ  ์๋ค๋ฉด ๋ฆฌํ๋ธ๋๊ฐ ๋๋ค.
    ๋ฐ๋ผ์ `ans++`ํ๊ณ  ํ์์ ๋ฉ์ถ๋ค.
```java
		for(int v : tree[node]) {

			if(v==tgt&&tree[node].size()==1) {
				//ํ์ฌ node๊ฐ ์ญ์ ํ  ๋ธ๋๋ง์ ์์์ผ๋ก ๊ฐ์ง๊ณ  ์๋ค. => ๋ฆฌํ๋ธ๋๊ฐ ๋๋ค	
				ans++;
				return;	
			}
			dfs(v);
		}
```



<br><br>

###  ๐ก ์์ค์ฝ๋


```java
package week23.BOJ_1068_G5_ํธ๋ฆฌ;

import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.Queue;
import java.util.StringTokenizer;

/**
 * 
 * 
 * โจ Algorithm โจ
 * @Problem : BOJ 1068 ํธ๋ฆฌ
 * @Author : Daun JO
 * @Date : 2021. 8. 7. 
 *
 */
public class Main_BOJ_1068_G5_ํธ๋ฆฌ {
	
	static int N, root, tgt, ans;
	static ArrayList<Integer>[] tree;
	public static void main(String[] args) throws Exception {
		
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st;
		
		/**
		 * ๋ธ๋ ์ง์ฐ๊ณ , ๋ฆฌํ๋ธ๋ ์ฐพ๊ธฐ
		 */
		
		N = Integer.parseInt(br.readLine()); //ํธ๋ฆฌ์ ๋ธ๋์ ๊ฐ์
		
		tree = new ArrayList[N];
		for(int i=0; i<N ; i++) {
			tree[i] = new ArrayList<>(); //์ด์งํธ๋ฆฌ์๋
		}
		
		st = new StringTokenizer(br.readLine());
		for(int i=0; i<N ; i++) {
			int parent = Integer.parseInt(st.nextToken()); //๊ฐ ๋ธ๋์ ๋ถ๋ชจ
			
			if(parent==-1) root = i; //๋ถ๋ชจ๊ฐ ์๋ค๋ฉด -1์ด ์ฃผ์ด์ง๋ค. ์ฆ ๋ฃจํธ์ด๋ค.
			else tree[parent].add(i);
		}
		
		tgt = Integer.parseInt(br.readLine()); //์ง์ธ ๋ธ๋์ ๋ฒํธ
		
		dfs(root); //root๋ถํฐ ํ์
		
		System.out.println(ans);
		
	}
	
	private static void dfs(int node) {
		if(node==tgt) return; //์ญ์ ํ  ๋ธ๋์ด๋ฉด ํ์ ์ค์ง
		
		if(tree[node].size()==0) {
			//์์์ด ์๋ค => ๋ฆฌํ๋ธ๋์ด๋ค.
			ans++;
			return;
		}
		
		for(int v : tree[node]) {

			if(v==tgt&&tree[node].size()==1) {
				//ํ์ฌ node๊ฐ ์ญ์ ํ  ๋ธ๋๋ง์ ์์์ผ๋ก ๊ฐ์ง๊ณ  ์๋ค. => ๋ฆฌํ๋ธ๋๊ฐ ๋๋ค	
				ans++;
				return;	
			}
			dfs(v);
		}
		
		
	}
	
	
}

```

<br><br>


###  ๐ฏ ์ฑ์  ๊ฒฐ๊ณผ
11604	88