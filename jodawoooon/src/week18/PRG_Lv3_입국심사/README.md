- μ΄λΆνμ
- level3



<br>


### π λ¬Έμ  μ€λͺ
https://programmers.co.kr/learn/courses/30/lessons/43238

nλͺμ΄ μκ΅­μ¬μ¬λ₯Ό μν΄ μ€μ μμ κΈ°λ€λ¦¬κ³  μμ΅λλ€. κ° μκ΅­μ¬μ¬λμ μλ μ¬μ¬κ΄λ§λ€ μ¬μ¬νλλ° κ±Έλ¦¬λ μκ°μ λ€λ¦λλ€.

μ²μμ λͺ¨λ  μ¬μ¬λλ λΉμ΄μμ΅λλ€. ν μ¬μ¬λμμλ λμμ ν λͺλ§ μ¬μ¬λ₯Ό ν  μ μμ΅λλ€. κ°μ₯ μμ μ μλ μ¬λμ λΉμ΄ μλ μ¬μ¬λλ‘ κ°μ μ¬μ¬λ₯Ό λ°μ μ μμ΅λλ€. νμ§λ§ λ λΉ¨λ¦¬ λλλ μ¬μ¬λκ° μμΌλ©΄ κΈ°λ€λ Έλ€κ° κ·Έκ³³μΌλ‘ κ°μ μ¬μ¬λ₯Ό λ°μ μλ μμ΅λλ€.

λͺ¨λ  μ¬λμ΄ μ¬μ¬λ₯Ό λ°λλ° κ±Έλ¦¬λ μκ°μ μ΅μλ‘ νκ³  μΆμ΅λλ€.

μκ΅­μ¬μ¬λ₯Ό κΈ°λ€λ¦¬λ μ¬λ μ n, κ° μ¬μ¬κ΄μ΄ ν λͺμ μ¬μ¬νλλ° κ±Έλ¦¬λ μκ°μ΄ λ΄κΈ΄ λ°°μ΄ timesκ° λ§€κ°λ³μλ‘ μ£Όμ΄μ§ λ, λͺ¨λ  μ¬λμ΄ μ¬μ¬λ₯Ό λ°λλ° κ±Έλ¦¬λ μκ°μ μ΅μκ°μ return νλλ‘ solution ν¨μλ₯Ό μμ±ν΄μ£ΌμΈμ.


#### μ νμ¬ν­
μκ΅­μ¬μ¬λ₯Ό κΈ°λ€λ¦¬λ μ¬λμ 1λͺ μ΄μ 1,000,000,000λͺ μ΄νμλλ€.
κ° μ¬μ¬κ΄μ΄ ν λͺμ μ¬μ¬νλλ° κ±Έλ¦¬λ μκ°μ 1λΆ μ΄μ 1,000,000,000λΆ μ΄νμλλ€.
μ¬μ¬κ΄μ 1λͺ μ΄μ 100,000λͺ μ΄νμλλ€.

#### μμΆλ ₯ μ
n	times	return
6	[7, 10]	28

#### μμΆλ ₯ μ μ€λͺ
κ°μ₯ μ²« λ μ¬λμ λ°λ‘ μ¬μ¬λ₯Ό λ°μΌλ¬ κ°λλ€.

7λΆμ΄ λμμ λ, μ²« λ²μ§Έ μ¬μ¬λκ° λΉκ³  3λ²μ§Έ μ¬λμ΄ μ¬μ¬λ₯Ό λ°μ΅λλ€.

10λΆμ΄ λμμ λ, λ λ²μ§Έ μ¬μ¬λκ° λΉκ³  4λ²μ§Έ μ¬λμ΄ μ¬μ¬λ₯Ό λ°μ΅λλ€.

14λΆμ΄ λμμ λ, μ²« λ²μ§Έ μ¬μ¬λκ° λΉκ³  5λ²μ§Έ μ¬λμ΄ μ¬μ¬λ₯Ό λ°μ΅λλ€.

20λΆμ΄ λμμ λ, λ λ²μ§Έ μ¬μ¬λκ° λΉμ§λ§ 6λ²μ§Έ μ¬λμ΄ κ·Έκ³³μμ μ¬μ¬λ₯Ό λ°μ§ μκ³  1λΆμ λ κΈ°λ€λ¦° νμ μ²« λ²μ§Έ μ¬μ¬λμμ μ¬μ¬λ₯Ό λ°μΌλ©΄ 28λΆμ λͺ¨λ  μ¬λμ μ¬μ¬κ° λλ©λλ€.
<br><br>

###  π‘ νμ΄

μ΄μ§νμμ μ΄μ©νλ©΄ κΈ°μ‘΄ νμ μκ°μ nμμ log2nμΌλ‘ μ€μΌ μ μλ€.  
λ¨ μ΄μ§νμ μ λ°μ΄ν°κ° μ λ ¬μ΄ λμ΄μμ΄μΌ νλ€.

μ΅μ, μ΅λ λ²μλ₯Ό κ΅¬νλ€ λ²μλ₯Ό μ’νκ°λ©° λ΅μ κ΅¬νλ€.

- μ΅μ λ²μ (left)λ 1*1μ΄λ€.
(μλκ° 1μ΄λ©° μ¬λμ΄ 1λͺμΌ κ²½μ°)
- μ΅λ λ²μ (right)λ times[times.length-1]*nμ΄λ€.
(μλκ° μ μΌ ν° μ¬μ¬λμ΄λ©° nλͺμ΄ μ¬μ¬ λ°λ κ²½μ°)

κ·Έλ¦¬κ³  μ€κ°κ°μΈ mid(left+right/2)κ° μκ΅­μ¬μ¬λ₯Ό κΈ°λ€λ¦¬λ μ¬λ λͺ¨λ(nλͺ)λ₯Ό μ¬μ¬ν  μ μλμ§ κ²μ¬νλ€.

μ¬μ¬ κ°λ₯ νλ€λ©΄ (>= n) answerμ midλ₯Ό λ£κ³  rightλ₯Ό λ μ€μ¬λ³Έλ€.  
μ¬μ¬ λΆκ°λ₯νλ€λ©΄ ( < n) leftλ₯Ό λλ €λ³Έλ€.


<br><br>

###  π‘ μμ€μ½λ
```
import java.util.*;
class Solution {
    public long solution(int n, int[] times) {
        
        //μ΄λΆνμ

        
        long answer = 0;
        
        //1. times λ°°μ΄ μ€λ¦μ°¨μ μ λ ¬
        Arrays.sort(times); //μκ° μ μ λ ¬
        
        //2. left = 1 (μλκ° 1μ΄λ©° μ¬λμ΄ 1λͺ) 
        //   right = μ μΌ μ€λ κ±Έλ¦¬λ μ¬μ¬κ΄μκ² λͺ¨λ μ¬μ¬λ°λ κ²½μ°
        long left = 1*1;
        long right = (long) times[times.length-1] * n;

        while(left <= right){
            long cnt = 0;
            long mid = (left+right)/2;
            
            for(int t : times){
                cnt += mid/t; 
                //mid κΈ°μ€ μ¬μ¬ν  μ μλ μ¬λ μ
            }
            
            if(cnt >= n){
                //nλͺμ μ¬μ¬ν  μ μλ€
                //answerμ midκ° λ£κ³ 
                answer = mid;
                //rightλ₯Ό μ€μ¬λ³Έλ€
                right = mid - 1;
                
            }else{
                //nλͺμ μ¬μ¬ν  μ μλ€
                //leftλ₯Ό λλ €λ³Έλ€
                left = mid + 1;
            }
        }
        return answer;
    }
}
```


<br>