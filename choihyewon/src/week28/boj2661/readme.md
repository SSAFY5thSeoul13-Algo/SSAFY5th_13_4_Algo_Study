## BOJ 2661 μ’μ μμ΄ 
- BackTracking
- π₯ Gold4
- π[μ’μ μμ΄ λ¬Έμ  λ°λ‘κ°κΈ°](https://www.acmicpc.net/problem/2661)



## νμ΄

μ΄ λ¬Έμ λ₯Ό νλ©΄μ λ°±νΈλνΉμ κ°λμ λͺνν λ€μ§κ² κ°μ΅λλ€!
λ¨Όμ  μμ΄μ μλ¦Ώμμ λ€μ΄κ° μ μλ λͺ¨λ  κ²½μ°λ₯Ό κ΅¬ν΄μ μ’μ μμ΄μΈ κ²½μ°μλ§ νμνλλ‘ μ§ννμμ΅λλ€.

~~~java
		for(int i=1; i<=3; i++) {
			if(isGood(str+i)) {
				backTracking(str+i);
			}
		}
~~~

μ’μ μμ΄μΈμ§ νλ³νλ ν¨μλ 
μμλ‘ strμ΄ 32121 μΈ κ²½μ° 
1μλ¦¬μμ© λΉκ΅ 321<u>2</u><u>1</u> -> λμΌνμ§ μμΌλ―λ‘ μ’μ μμ΄ 
2μλ¦¬μμ© λΉκ΅ 3<u>21</u><u>21</u> -> λμΌνλ―λ‘ λμ μμ΄ 
μ΄λ κ² νλ³ν΄μ£Όμμ΅λλ€.

~~~java
	private static boolean isGood(String str) {
		// μμ΄μ λͺ¨λ  κ²½μ°λ₯Ό νμ
		for(int i=1; i<=str.length()/2; i++) {
			String str1 = str.substring(str.length()-i-i, str.length()-i);
			String str2 = str.substring(str.length()-i,str.length());
			// λ§μ½ λμ μμ΄μ΄λΌλ©΄ false return 
			if(str1.equals(str2)) {
				return false;
			}
		}
		
		return true;
		
	}
~~~

κ·Έλ¦¬κ³  κ°μ₯ λ¨Όμ  λμ¨ μμ΄μ΄ NκΈΈμ΄μ μ μΌ μμ μμ΄μ΄κΈ° λλ¬Έμ isEnd λ³μλ₯Ό ν΅ν΄ κ²°κ³Όλ₯Ό μΆλ ₯νκ³  λ©μΆκ² ν΄μ£Όμμ΅λλ€.


## μμ€μ½λ
~~~java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.*;

public class BOJ_2661_G4_μ’μμμ΄ {
	static int N;
	static boolean isEnd = false;
	static List<Integer> list = new ArrayList<>();
	public static void main(String[] args) throws Exception{
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		N = Integer.parseInt(br.readLine());
		String str = "";
		
		backTracking(str);

	}
	private static void backTracking(String str) {
		// μ μΌ μμ μμ΄μ΄ λμμΌλ―λ‘ νμ μ’λ£ 
		if(isEnd) {
			return;
		}
		
		if(str.length()==N) {
			System.out.println(str);
			// μ’λ£λμμμ μλ―Έ 
			isEnd = true;
			return;
		}
		
		// μ«μλ 1,2,3 μΌλ‘λ§ μ΄λ£¨μ΄μ Έ μμΌλ―λ‘ 1λΆν° 3κΉμ§ λ°λ³΅ 
		for(int i=1; i<=3; i++) {
			if(isGood(str+i)) {
				backTracking(str+i);
			}
		}
		
	}
	// μ’μ μμ΄μΈμ§ μλμ§ νλ³ 
	private static boolean isGood(String str) {
		// μμ΄μ λͺ¨λ  κ²½μ°λ₯Ό νμ
		for(int i=1; i<=str.length()/2; i++) {
			String str1 = str.substring(str.length()-i-i, str.length()-i);
			String str2 = str.substring(str.length()-i,str.length());
			// λ§μ½ λμ μμ΄μ΄λΌλ©΄ false return 
			if(str1.equals(str2)) {
				return false;
			}
		}
		
		return true;
		
	}


}

~~~

## κ²°κ³Ό 

| λ©λͺ¨λ¦¬  | μκ° |
|----|----|
| 11956kb| 80ms|
