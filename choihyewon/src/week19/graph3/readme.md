## Programmers - ๋ฐฉ์ ๊ฐ์ 
- Graph , HashSet 
- Level3

๐[๋ฐฉ์ ๊ฐ์ ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://programmers.co.kr/learn/courses/30/lessons/49190)

## ํ์ด
์ ๋ ์ต๋ 10๋ง๋ฒ ์ด๋์ด ๊ฐ๋ฅํ๊ธฐ ๋๋ฌธ์ ๋ฐฐ์ด๋์  HashSet์ ์ฌ์ฉํด์ฃผ์์ต๋๋ค.

~~~java
		// ๋ฐฉ๋ฌธํ ์ ์  ๊ด๋ฆฌ๋ฅผ ์ํ set 
        Set<Node> node = new HashSet<>();
        // ๋ฐฉ๋ฌธํ ๊ฐ์  ๊ด๋ฆฌ๋ฅผ ์ํ set 
        Set<Edge> edge = new HashSet<>();
~~~
์ ์ , ๊ฐ์ ์ ๊ฐ์ฒด๋ฅผ ๋ง๋ค๊ณ  ๊ฐ ๊ฐ์ฒด๋ฅผ HashSet์ ์ ์ฅํ ๋ ๊ฐ์ ๊ฐ์ฒด๋ฅผ ๋ํ๋ด๋ ์กฐ๊ฑด์ ์ฌ์ ์ํด์ฃผ๊ธฐ ์ํด์ Equals, hashCode ๋ฉ์๋๋ฅผ ์ฌ์ ์ํด์ฃผ์์ต๋๋ค.

~~~java
	class Node{
		int y;
		int x;
		public Node(int y,int x) {
			this.y = y;
			this.x = x;
		}
		@Override
		public boolean equals(Object o) {
			Node n = (Node) o;
			
			if(this.y==n.y && this.x==n.x)
				return true;
			return false;
			
		}
		@Override
		public int hashCode() {
			int prime = 31;
			int hashcode = 1;
			
			hashcode = prime * hashcode + this.y;
			hashcode = prime * hashcode + this.x;
			
			return hashcode;
		}
	}
	class Edge{
		int start_y;
		int start_x;
		int end_y;
		int end_x;
		int dir;
		public Edge(int start_y,int start_x, int end_y,int end_x,int dir) {
			this.start_y = start_y;
			this.start_x = start_x;
			this.end_y = end_y;
			this.end_x = end_x;
			this.dir = dir;
		}
		@Override
		public boolean equals(Object o) {
			Edge e = (Edge) o;
			
			if((this.start_y + this.end_y == e.start_y + e.end_y) && (this.start_x + this.end_x == e.start_x + e.end_x) && (Math.abs(e.dir-this.dir) == 4 || e.dir==this.dir)) {
				return true;
			}
			return false;
			
		}
		@Override
		public int hashCode() {
			int prime = 31;
			int hashcode = 1;
			
			hashcode = prime * hashcode + (this.start_y + this.end_y);
			hashcode = prime * hashcode + (this.start_x + this.end_x);
			hashcode = prime * hashcode + this.dir;
			
			return hashcode;
		}
		
	}
~~~

๋๊ฐ์ ์ผ๋ก ์ด๋ํ๋ ๊ฒฝ์ฐ ๋ค๋ฅธ ๊ฐ์ ๊ณผ ๊ฒน์น๋ ํ์๋์ง ์๋ ์ ์ ๋๋ฌธ์ ์ํ๋ ๋ฐฉ์ ๊ฐ์๋ฅผ ๊ตฌํ์ง ๋ชปํ๋ฏ๋ก ์ด๋์ 2๋ฒ ๋ฐ๋ณตํด์ค๋๋ค. 

~~~java
	for(int i=0; i<arrows.length; i++) {
        	// ํ์ฌ ๋ฐฉํฅ 
        	int d = arrows[i];
        	// 2๋ฒ ์ด๋ 
        	for(int j=0; j<2; j++) {
        		int ny = y + dy[d];
        		int nx = x + dx[d];
        		
        		Node next_node = new Node(ny,nx);
        		Edge next_edge = new Edge(y,x,ny,nx,d);

        		// ๋ฐฉ๋ฌธํ ์ ์ ์ด์ง๋ง ๋ค์ด์จ ๋ฐฉํฅ์ด ๋ค๋ฅธ ๊ฒฝ์ฐ ๋ฐฉ count 
        		if(node.contains(next_node) && !edge.contains(next_edge)) {
        			answer++;
        		}
        		// ๋ฐฉ๋ฌธํ ์ ์ด ์๋ค๋ฉด ์ ์ set์ ์ถ๊ฐ 
        		else {
        			node.add(next_node);
        		}
        		
        	
        		// ํ์ฌ ๋ฐฉํฅ์ ๊ฐ์ ๊ณผ ๋ฐ๋ ๋ฐฉํฅ ๊ฐ์  ์ถ๊ฐ 
        		edge.add(next_edge);
        		edge.add(new Edge(ny,nx,y,x,(d+4)%8));
        		y = ny;
        		x = nx;
        		
        	}
        	
        }
~~~


## ๋งํ์  
๋ฌธ์  ํ์ด ๋ฐฉ๋ฒ์ ๋ ์ฌ๋ฆฌ์ง ๋ชปํ์ฌ ๋ธ๋ก๊ทธ ํ์ด๋ฅผ ์ฐธ์กฐํ์์ต๋๋ค. 

## ์์ค์ฝ๋
~~~java
import java.util.*;

public class ๋ฐฉ์_๊ฐ์ {
	static int[] dy = {-1,-1,0,1,1,1,0,-1};
	static int[] dx = {0,1,1,1,0,-1,-1,-1};
	class Node{
		int y;
		int x;
		public Node(int y,int x) {
			this.y = y;
			this.x = x;
		}
		@Override
		public boolean equals(Object o) {
			Node n = (Node) o;
			
			if(this.y==n.y && this.x==n.x)
				return true;
			return false;
			
		}
		@Override
		public int hashCode() {
			int prime = 31;
			int hashcode = 1;
			
			hashcode = prime * hashcode + this.y;
			hashcode = prime * hashcode + this.x;
			
			return hashcode;
		}
	}
	class Edge{
		int start_y;
		int start_x;
		int end_y;
		int end_x;
		int dir;
		public Edge(int start_y,int start_x, int end_y,int end_x,int dir) {
			this.start_y = start_y;
			this.start_x = start_x;
			this.end_y = end_y;
			this.end_x = end_x;
			this.dir = dir;
		}
		@Override
		public boolean equals(Object o) {
			Edge e = (Edge) o;
			
			if((this.start_y + this.end_y == e.start_y + e.end_y) && (this.start_x + this.end_x == e.start_x + e.end_x) && (Math.abs(e.dir-this.dir) == 4 || e.dir==this.dir)) {
				return true;
			}
			return false;
			
		}
		@Override
		public int hashCode() {
			int prime = 31;
			int hashcode = 1;
			
			hashcode = prime * hashcode + (this.start_y + this.end_y);
			hashcode = prime * hashcode + (this.start_x + this.end_x);
			hashcode = prime * hashcode + this.dir;
			
			return hashcode;
		}
		
	}
	public int solution(int[] arrows) {
        int answer = 0;
        
        // ๋ฐฉ๋ฌธํ ์ ์  ๊ด๋ฆฌ๋ฅผ ์ํ set 
        Set<Node> node = new HashSet<>();
        // ๋ฐฉ๋ฌธํ ๊ฐ์  ๊ด๋ฆฌ๋ฅผ ์ํ set 
        Set<Edge> edge = new HashSet<>();
        
        // (0,0)์์ ์์ 
        int y = 0;
        int x = 0;
        
        node.add(new Node(y,x));
        
        for(int i=0; i<arrows.length; i++) {
        	// ํ์ฌ ๋ฐฉํฅ 
        	int d = arrows[i];
        	// 2๋ฒ ์ด๋ 
        	for(int j=0; j<2; j++) {
        		int ny = y + dy[d];
        		int nx = x + dx[d];
        		
        		Node next_node = new Node(ny,nx);
        		Edge next_edge = new Edge(y,x,ny,nx,d);

        		// ๋ฐฉ๋ฌธํ ์ ์ ์ด์ง๋ง ๋ค์ด์จ ๋ฐฉํฅ์ด ๋ค๋ฅธ ๊ฒฝ์ฐ ๋ฐฉ count 
        		if(node.contains(next_node) && !edge.contains(next_edge)) {
        			answer++;
        		}
        		// ๋ฐฉ๋ฌธํ ์ ์ด ์๋ค๋ฉด ์ ์ set์ ์ถ๊ฐ 
        		else {
        			node.add(next_node);
        		}
        		
        	
        		// ํ์ฌ ๋ฐฉํฅ์ ๊ฐ์ ๊ณผ ๋ฐ๋ ๋ฐฉํฅ ๊ฐ์  ์ถ๊ฐ 
        		edge.add(next_edge);
        		edge.add(new Edge(ny,nx,y,x,(d+4)%8));
        		y = ny;
        		x = nx;
        	}
        	
        }
        
        
        return answer;
    }

}

~~~

## ๊ฒฐ๊ณผ 

| ์ ํ์ฑ  | ํ์คํธ |
|----|----|
|ํ์คํธ 1 |	ํต๊ณผ (1.21ms, 52.2MB)|
|ํ์คํธ 2 |	ํต๊ณผ (2.81ms, 52.9MB)|
|ํ์คํธ 3 |	ํต๊ณผ (3.41ms, 52.3MB)|
|ํ์คํธ 4 |	ํต๊ณผ (6.17ms, 54.2MB)|
|ํ์คํธ 5 |	ํต๊ณผ (43.49ms, 60.5MB)|
|ํ์คํธ 6 |	ํต๊ณผ (282.65ms, 103MB)|
|ํ์คํธ 7 |	ํต๊ณผ (20.72ms, 57.3MB)|
|ํ์คํธ 8 |	ํต๊ณผ (249.02ms, 97.3MB)|
|ํ์คํธ 9 |	ํต๊ณผ (307.92ms, 112MB)|