## BOJ 16398 G4 νμ±μ°κ²°
- MST (Kruskal)
- G4



<br><br>


### π λ¬Έμ  μ€λͺ
https://www.acmicpc.net/problem/16398

νμ΅ μ κ΅­μ μ€μ¬μ νμ± Tμ΄λ€. μ κ΅­μ ν©μ  μ€μμ΄λ νμ± Tμμ μ κ΅­μ ν¨κ³Όμ μΌλ‘ ν΅μΉνκΈ° μν΄μ, Nκ°μ νμ± κ°μ νλ‘μ°λ₯Ό μ€μΉνλ €κ³  νλ€.

λ νμ± κ°μ νλ‘μ°λ₯Ό μ€μΉνλ©΄ μ κ΅­μ ν¨μ κ³Ό λ¬΄μ­μ λ€μ ν νμ±μμ λ€λ₯Έ νμ±μΌλ‘ λ¬΄μν  μ μμ λ§νΌ μ§§μ μκ°λ§μ μ΄λν  μ μλ€. νμ§λ§, μΉμμ μ μ§νκΈ° μν΄μ νλ‘μ° λ΄μ μ κ΅­κ΅°μ μ£ΌλμμΌμΌ νλ€.

λͺ¨λ  νμ± κ°μ νλ‘μ°λ₯Ό μ€μΉνκ³  νλ‘μ° λ΄μ μ κ΅­κ΅°μ μ£Όλνλ©΄, μ κ΅­μ μ μ μ΄ μνλκΈ° λλ¬Έμ ν©μ  μ€μμ΄λ μ κ΅­μ λͺ¨λ  νμ±μ μ°κ²°νλ©΄μ νλ‘μ° κ΄λ¦¬ λΉμ©μ μ΅μνμΌλ‘ νλ € νλ€.

Nκ°μ νμ±μ μ μ 1,β¦,NμΌλ‘ νμνκ³ , νμ± iμ νμ± jμ¬μ΄μ νλ‘μ° κ΄λ¦¬λΉμ©μ Cijμ΄λ©°, i = jμΈ κ²½μ° ν­μ 0μ΄λ€.

μ κ΅­μ μ°Έλͺ¨μΈ λΉμ μ μ κ΅­μ ν©μ  μ€μμ΄λ₯Ό λμ μ κ΅­ λ΄ λͺ¨λ  νμ±μ μ°κ²°νκ³ , κ·Έ μ μ§λΉμ©μ μ΅μννμ.  μ΄λ νλ‘μ°μ μ€μΉλΉμ©μ λ¬΄μνκΈ°λ‘ νλ€.
<br>

#### β μλ ₯
μλ ₯μΌλ‘ μ²« μ€μ νμ±μ μ N (1 β€ N β€ 1000)μ΄ μ£Όμ΄μ§λ€.

λ λ²μ§Έ μ€λΆν° N+1μ€κΉμ§ κ° νμ±κ°μ νλ‘μ° κ΄λ¦¬ λΉμ©μ΄ N x N νλ ¬ (Cij),  (1 β€ i, j β€ N, 1 β€ Cij β€ 100,000,000, Cij = Cji) λ‘ μ£Όμ΄μ§λ€.
<br>

#### β μΆλ ₯
λͺ¨λ  νμ±μ μ°κ²°νμ λ, μ΅μ νλ‘μ°μ κ΄λ¦¬λΉμ©μ μΆλ ₯νλ€.
<br>


<br>

###  π‘ νμ΄

λͺ¨λ  νμ±μ μ°κ²°νμ λ μ΅μ λΉμ© -> MST

ν¬λ£¨μ€μΉΌ μκ³ λ¦¬μ¦μΌλ‘ νμλ€.

Nκ°μ νμ±μ΄ μμ λ μ΅μλΉμ©μΌλ‘ N-1κ°μ κ°μ μ μ΄μ©ν΄ λͺ¨λ  νμ±μ μ°κ²°νλ€.

 
<br><br>

###  π¬ μμ€μ½λ

```java
package week25.BOJ_16398_G4_νμ±μ°κ²°;

import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.ArrayList;
import java.util.Collections;
import java.util.StringTokenizer;

/***
 * 
 * 
 * β¨ Algorithm β¨
 * @Problem : BOJ 16398 νμ±μ°κ²°
 * @Author : Daun JO
 * @Date : 2021. 9. 6. 
 * @Algorithm : MST (Kruskal)
 *
 */
public class Main_BOJ_16398_G4_νμ±μ°κ²° {
	
	static int N, parents[];
	static long ans;
	static ArrayList<Edge> edgeList = new ArrayList<>();
	static class Edge implements Comparable<Edge>{
		
		int from, to, cost;

		public Edge(int from, int to, int cost) {
			super();
			this.from = from;
			this.to = to;
			this.cost = cost;
		}

		@Override
		public int compareTo(Edge o) {
			// TODO Auto-generated method stub
			return Integer.compare(this.cost, o.cost);
		}
	}
	public static void main(String[] args) throws Exception {
		
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		StringTokenizer st;
		
		N = Integer.parseInt(br.readLine()); //νμ±μ μ

		parents = new int[N];
		
		for (int i = 0; i < N; i++) {
			st = new StringTokenizer(br.readLine());
			for (int j = 0; j < N; j++) {

				int cost = Integer.parseInt(st.nextToken());
				edgeList.add(new Edge(i,j, cost));
			}
		}
		
		Collections.sort(edgeList);
		
		make();
		
		int cnt = 0;
		
		for(Edge edge : edgeList) {
			if(union(edge.from, edge.to)) {
				ans += edge.cost;
				cnt++;
				
				if(cnt==N-1) break;
			}
		}
		
		System.out.println(ans);
		
	}
	private static boolean union(int from, int to) {
		int fRoot = findSet(from);
		int tRoot = findSet(to);
		
		if(fRoot==tRoot) return false;
		parents[tRoot] = fRoot;
		return true;
	}
	private static int findSet(int v) {
		if(parents[v]==v) return v;
		return parents[v] = findSet(parents[v]);
	}
	private static void make() {
		for (int i = 0; i < N; i++) {
			parents[i] = i;
		}
	}

}


```
<br><br>


###  π― μ±μ  κ²°κ³Ό
174644	1240