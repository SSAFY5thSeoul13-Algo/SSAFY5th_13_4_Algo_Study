## BOJ 7682 ํฑํํ  
- Simulation 
- ๐ฅ Gold5
- ๐[ํฑํํ  ๋ฌธ์  ๋ฐ๋ก๊ฐ๊ธฐ](https://www.acmicpc.net/problem/7682)



## ํ์ด

์ ๋ ๊ฐ๊ฐ์ ์กฐ๊ฑด์ ๋ฐ๋ผ ๊ตฌํํ์์ต๋๋ค. 
๋จผ์  ๊ฒฉ์ํ์ ๋ชจ๋  ๋ง์ด ์์ ๊ฒฝ์ฐ ๋ง์ ์ด ํฉ์ 9๊ฐ ๋๊ณ  ์ด๋ X ๊ฐ์๋ O๋ณด๋ค 1๋ ๋ง์์ผ ํฉ๋๋ค.
์ด ๊ฒฝ์ฐ์๋ X๊ฐ ์ด๊ธฐ๋ฉด์ O๊ฐ ์ง๊ฑฐ๋, X,O ๋ชจ๋ ์ก์๊ฒฝ์ฐ (=๋น๊ธด๊ฒฝ์ฐ) ํฑํํ ๊ฐ ๊ฐ๋ฅํฉ๋๋ค.

~~~java
		if(sum==9 && xCnt==oCnt+1) {
			if(isWin('X') && !isWin('O')) {
				return true;
			}else if(!isWin('X') && !isWin('O')) {
				return true;
			}else {
				return false;
			}
		}
~~~

๊ฒฉ์ํ์์ ๋ง์ด ๋ค ์์ง ์์ ๊ฒฝ์ฐ ๋ ๋ง์ ๊ฐ์๊ฐ ๊ฐ๋ค๋ฉด O๊ฐ ๋ง์ง๋ง์ผ๋ก ๋์์ผ๋ฏ๋ก ๋ฌด์กฐ๊ฑด O๊ฐ ์ด๊ฒจ์ผํฉ๋๋ค. X๊ฐ O๋ณด๋ค ํด๊ฒฝ์ฐ์๋ X๋ฅผ ๋ง์ง๋ง์ผ๋ก ๋์ ๊ฒฝ์ฐ์ด๋ฏ๋ก ๋ฌด์กฐ๊ฑด X๊ฐ ์ด๊ฒจ์ผํฉ๋๋ค.

~~~java
else {
			// ๋๊ฐ์ ๊ฐ์๊ฐ ๊ฐ์ ๊ฒฝ์ฐ 
			if(xCnt == oCnt) {
				if(isWin('O') && !isWin('X')) {
					return true;
				}else {
					return false;
				}
			}
			// X๊ฐ O๋ณด๋ค 1๊ฐ ๋ ๋ง์ ๊ฒฝ์ฐ 
			else if(xCnt==oCnt+1) {
				if(!isWin('O') && isWin('X')) {
					return true;
				}else {
					return false;
				}
			}
			
		}
~~~

## ๋งํ ์  
์ธ์ธํ ์กฐ๊ฑด์ ์ฃผ์ด์ผํ๊ธฐ๋๋ฌธ์ ๊ตฌํ๋ถ๋ถ์ ์ด๋ ต์ง ์์์ผ๋ ํ์คํธ์ผ์ด์ค์์ ํ๋ฆฌ๋ ๊ฒฝ์ฐ๊ฐ ์์์ต๋๋ค.

## ์์ค์ฝ๋
~~~java
import java.util.*;
import java.io.*;
public class BOJ_7682_G5_ํฑํํ  {
	static char[][] arr;
	public static void main(String[] args)throws Exception {
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		
		while(true) {
			String str = br.readLine();
			
			if(str.equals("end")) {
				break;
			}
			
			arr = new char[3][3];
			for(int i=0; i<9; i++) {
				arr[i/3][i%3] = str.charAt(i);
			}
			
			if(tictactoc()) {
				System.out.println("valid");
			}else {
				System.out.println("invalid");
			}
			
		}

	}
	private static boolean tictactoc() {
		int xCnt = 0;
		int oCnt = 0;
		int sum = 0;
		
		for(int i=0; i<3; i++) {
			for(int j=0; j<3; j++) {
				if(arr[i][j]=='X') {
					xCnt++;
				}else if(arr[i][j] == 'O') {
					oCnt++;
				}
			}
		}
		sum = xCnt + oCnt;
		
		if(xCnt<oCnt) {
			return false;
		}
		
		// ๊ฒ์์ด ๋๋ ๊ฒฝ์ฐ X๋ถํฐ ์์ํ๋ฏ๋ก X๊ฐ 5๊ฐ, O๊ฐ 4๊ฐ ์ฌ์ผํ๋ค.
		// ์ด ๊ฒฝ์ฐ ๋ง์ง๋ง์ X๋ก ๋๋์ผ ์ฑ๋ฆฝ๋๋ฏ๋ก X๊ฐ ์ด๊ธฐ๊ฑฐ๋ ๋น๊ฒจ์ผํ๋ค.
		if(sum==9 && xCnt==oCnt+1) {
			if(isWin('X') && !isWin('O')) {
				return true;
			}else if(!isWin('X') && !isWin('O')) {
				return true;
			}else {
				return false;
			}
		}else {
			// ๋๊ฐ์ ๊ฐ์๊ฐ ๊ฐ์ ๊ฒฝ์ฐ 
			if(xCnt == oCnt) {
				if(isWin('O') && !isWin('X')) {
					return true;
				}else {
					return false;
				}
			}
			// X๊ฐ O๋ณด๋ค 1๊ฐ ๋ ๋ง์ ๊ฒฝ์ฐ 
			else if(xCnt==oCnt+1) {
				if(!isWin('O') && isWin('X')) {
					return true;
				}else {
					return false;
				}
			}
			
		}
		
		return false;
		
	}
	// ์ด๊ฒผ์ผ๋ฉด true return 
	private static boolean isWin(char c) {
		// ๊ฐ๋ก ๋น๊ณ  
		for(int i=0; i<3; i++) {
			if(arr[i][0] == c && arr[i][1] == c && arr[i][2] == c) {
				return true;
			}
		}
		
		// ์ธ๋ก ๋น๊ณ  
		for(int i=0; i<3; i++) {
			if(arr[0][i] == c && arr[1][i] == c && arr[2][i] == c) {
				return true;
			}
		}
		
		// ๋๊ฐ์  ๋น๊ณ  
		if(arr[0][0] == c && arr[1][1] == c && arr[2][2] == c) {
			return true;
		}
		if(arr[0][2] == c && arr[1][1] == c && arr[2][0] == c) {
			return true;
		}

		
		return false;
	}

}

~~~

## ๊ฒฐ๊ณผ 

| ๋ฉ๋ชจ๋ฆฌ  | ์๊ฐ |
|----|----|
|11284kb| 84ms|