## Programmers - ๊ธฐ๋ฅ๊ฐ๋ฐ 
- Queue
- Level2

๐[๊ธฐ๋ฅ๊ฐ๋ฐ ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://programmers.co.kr/learn/courses/30/lessons/42586)

## ํ์ด
๋จผ์  index์ ์์์ ์ง๋ก๋ฅผ ๋ด๊ณ  ์๋ Work ๊ฐ์ฒด๋ฅผ ์์ฑํ์ฌ Queue์ ๋ด์์ค๋๋ค.

~~~java
static class Work{
		int idx;
		int progress;
		public Work(int idx,int progress) {
			this.idx = idx;
			this.progress = progress;
		}
	}
~~~

๊ทธ๋ฆฌ๊ณ  ํ์ ๋ด๊ธด ๋ชจ๋  ์์์ด ๋ค ๋ฐฐํฌ๊ฐ ๋ ๋๊น์ง (ํ๊ฐ ๋น์ด์์ผ๋ฉด ๋ฐ๋ณต๋ฌธ ์ข๋ฃ) ํ์ฌ ์์๋ + ๋ฐฐํฌ์ผ์*๊ฐ๋ฐ์๋ ๊ฐ์ ๋น๊ตํ์ฌ 100๋ณด๋ค ๊ฐ๊ฑฐ๋ ํฌ๋ค๋ฉด ๋ฐฐํฌ๋ฅผ ํ  ์ ์์ผ๋ฏ๋ก ํ์์ ๋นผ์ฃผ๊ณ  ๊ทธ๋  ํ๋ฃจ์ ๋ฐฐํฌ๊ฐ ๋ ์์์ count๋ฅผ ํด์ฃผ์์ต๋๋ค.

~~~java
	while(!queue.isEmpty()) {
        		Work work = queue.peek();
        		int idx = work.idx;
        		int progress = work.progress;
        		int tmp = progress + speeds[idx]*day;
        		if(tmp>=100) {
        			// ๋ฐฐํฌ๋ฅผ ํ  ์ ์๋ค๋ฉด queue์์ poll
        			queue.poll();
        			// ๋ฐฐํฌ์ ์์์ ๊ฐ์ count
        			cnt++;
        		}else {
        			break;
        		}
        	}
~~~

count๋ฅผ ํ์๋ 0์ด๋ผ๋ฉด, ๊ทธ๋  ํ๋ฃจ๋ ๋ฐฐํฌ๋ ์์์ด ์์ผ๋ฏ๋ก answer์ ๋ฃ์ ๊ฐ์ด ์์ต๋๋ค.


## ์์ค์ฝ๋
~~~java
import java.util.*;

public class Programmers_๊ธฐ๋ฅ๊ฐ๋ฐ {
	static class Work{
		int idx;
		int progress;
		public Work(int idx,int progress) {
			this.idx = idx;
			this.progress = progress;
		}
	}
	public int[] solution(int[] progresses, int[] speeds) {
        List<Integer> list = new ArrayList<>();
        Queue<Work> queue = new LinkedList<>();
 
        for(int i=0; i<progresses.length; i++) {
        	queue.add(new Work(i,progresses[i]));
        }
        
        int day = 0;
        while(!queue.isEmpty()) {
        	day++;
        	int cnt = 0;
        	while(!queue.isEmpty()) {
        		Work work = queue.peek();
        		int idx = work.idx;
        		int progress = work.progress;
        		int tmp = progress + speeds[idx]*day;
        		if(tmp>=100) {
        			// ๋ฐฐํฌ๋ฅผ ํ  ์ ์๋ค๋ฉด queue์์ poll
        			queue.poll();
        			// ๋ฐฐํฌ์ ์์์ ๊ฐ์ count
        			cnt++;
        		}else {
        			break;
        		}
        	}
        	
        	// ๋ฐฐํฌ๋ฅผ ํ ๊ฒฝ์ฐ์๋ง list์ ๋ด๋๋ค.
        	if(cnt!=0) {
        		list.add(cnt);
        	}
        	
        	
        }
        
        int[] answer = new int[list.size()];
        for(int i=0; i<list.size(); i++) {
        	answer[i] = list.get(i);
        }
        
        return answer;
    }

}
~~~

## ๊ฒฐ๊ณผ 

| ์ ํ์ฑ  | ํ์คํธ |
|----|----|
|ํ์คํธ 1 |	ํต๊ณผ (0.27ms, 52MB)|
|ํ์คํธ 2 |	ํต๊ณผ (0.60ms, 52.1MB)|
|ํ์คํธ 3 |	ํต๊ณผ (0.44ms, 51.9MB)|
|ํ์คํธ 4 |	ํต๊ณผ (0.45ms, 52.4MB)|
|ํ์คํธ 5 |	ํต๊ณผ (0.39ms, 53.5MB)|
|ํ์คํธ 6 |	ํต๊ณผ (0.36ms, 52.8MB)|
|ํ์คํธ 7 |	ํต๊ณผ (0.53ms, 52.7MB)|
|ํ์คํธ 8 |	ํต๊ณผ (3.42ms, 52.5MB)|
|ํ์คํธ 9 |	ํต๊ณผ (0.48ms, 52MB)|
|ํ์คํธ 10 |	ํต๊ณผ (0.50ms, 52.2MB)|
|ํ์คํธ 11 |	ํต๊ณผ (0.38ms, 52.5MB)|