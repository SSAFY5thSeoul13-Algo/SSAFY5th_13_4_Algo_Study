## Programmers - ์์ 
- DFS 
- Level3

๐[N์ผ๋ก ํํ ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://programmers.co.kr/learn/courses/30/lessons/42895)

## ํ์ด
์๋ ์นดํ๊ณ ๋ฆฌ๊ฐ dp๋ก ๋์ด์์์ผ๋ dp๋ก ํด๊ฒฐํ์ง ๋ชปํ์ฌ dfs๋ฅผ ์ด์ฉํ์ฌ ๋ฌธ์ ๋ฅผ ํ์์ต๋๋ค.
๋ง๋ค ์ ์๋ ๋ชจ๋  ์๋ฅผ ๊ฐ์ง๊ณ  ์ฌ์น์ฐ์ฐ์ ํ์ฌ N ์ฌ์ฉํ์๊ฐ 8๋ณด๋ค ๋ ํฐ ๊ฒฝ์ฐ์๋ -1์ answer์ ์ ์ฅํ์ฌ return ํด์ฃผ์์ต๋๋ค.
๊ทธ๋ฆฌ๊ณ  ์๋ฅผ ๋ค์ด N์ด 5์ธ ๊ฒฝ์ฐ, 5 ์ธ์๋ 55,555,5555... ์ด๋ฐ ์ซ์๋ฅผ ์ฐ์ฐํ๊ธฐ ์ํด

~~~java
tmp = tmp * 10 + N;
~~~
๋ถ๋ถ์ ํตํด N์ด ์ฐ์์ธ ์ซ์๋ฅผ ๋ง๋ค์ด ๋ง์, ๋บ์, ๊ณฑ์, ๋๋์ ์ฌ์น์ฐ์ฐ์ ์งํํด์ฃผ์ด N ์ฌ์ฉํ์์ ์ต์๊ฐ์ ๊ตฌํ์์ต๋๋ค.

 

## ์์ค์ฝ๋
~~~java
class Solution {
    static int answer = 9;
	public int solution(int N, int number) {
        dfs(N, number, 0, 0);
        
        if(answer == 9)
            return -1;
        return answer;
    }

	private void dfs(int N, int number, int cnt, int result) {
		// ์ต์๊ฐ์ด 8๋ณด๋ค ํฌ๋ฉด -1 return
		if(cnt > 8) {
			answer = -1;
			return;
		}
		
		if(result==number) {
			answer = Math.min(answer, cnt);
            return;
		}
		
		int tmp = N;
		for(int i=0; i<8-cnt; i++) {
			dfs(N, number, cnt+i+1, result+tmp);
			dfs(N, number, cnt+i+1, result-tmp);
			dfs(N, number, cnt+i+1, result*tmp);
			dfs(N, number, cnt+i+1, result/tmp);
            tmp = tmp * 10 + N;
		}
		
		
	}
}

~~~

## ๊ฒฐ๊ณผ 

| ์ ํ์ฑ  | ํ์คํธ |
|----|----|
|ํ์คํธ 1 |	ํต๊ณผ (5.08ms, 52.1MB)|
|ํ์คํธ 2 |	ํต๊ณผ (6.49ms, 52.6MB)|
|ํ์คํธ 3 |	ํต๊ณผ (5.49ms, 53.8MB)|
|ํ์คํธ 4 |	ํต๊ณผ (5.62ms, 51.8MB)|
|ํ์คํธ 5 |	ํต๊ณผ (4.24ms, 52.2MB)|
|ํ์คํธ 6 |	ํต๊ณผ (5.55ms, 52.5MB)|
|ํ์คํธ 7 |	ํต๊ณผ (5.04ms, 51.7MB)|
|ํ์คํธ 8 |	ํต๊ณผ (6.15ms, 53MB)|
|ํ์คํธ 9 |	ํต๊ณผ (3.37ms, 52.3MB)|