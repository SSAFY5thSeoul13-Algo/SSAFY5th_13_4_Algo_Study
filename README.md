

#  ๐ก ์๊ณ ๋ฆฌ์ฆ ์คํฐ๋ ๐ก

SSAFY 5๊ธฐ ์์ธ 13๋ฐ ์๊ณ ๋ฆฌ์ฆ ์คํฐ๋ ๊ธฐ๋ก

 - [ ] ์์ธ 13๋ฐ 4์กฐ ๋ฌธ์ฑ์ฑ
 - [ ] ์์ธ 13๋ฐ 4์กฐ ์กฐ๋ค์ด
 - [ ] ์์ธ 13๋ฐ 4์กฐ ์กฐํ๋ฏผ
 - [ ] ์์ธ 13๋ฐ 4์กฐ ์ตํ์
<br><br>

## ๐ Rule
๊ฐ์ ๋ฌธ์ ๋ฅผ ์ ์ ํ์ฌ ๋งค์ฃผ 4~12๋ฌธ์ ๋ฅผ ํ๋๋ค.
๋งค์ฃผ ์์์ผ ์นด์นด์คํก ๊ณต์ง๋ฐฉ์ ๋๊ธ๋ก ๋ฌธ์ ๋ฅผ ๋ฑ๋กํฉ๋๋ค.
* โโ ๋ฌธ์ ํ์ด ๋ง๊ฐ : ๋งค์ฃผ ์ผ์์ผ 20:00 ๊น์ง
* โโ ๋ฆฌ๋ทฐ ๋ง๊ฐ : ๋งค์ฃผ ์์์ผ 23:59 ๊น์ง
<br><br>

## ๐ Convention
###  1๏ธโฃ Code Convention
๊ฐ ์ฝ๋ ๋ณ ๋ชฉ์ ์ ์ฃผ์์ผ๋ก ์์ฑํฉ๋๋ค.
๋ณ์์ ํจ์ ์ด๋ฆ ๋ํ ์ญํ ์ ์ ์ ์๋๋ก ๊ฐ๋จํ ์ฃผ์์ ๋ง๋ถ์๋๋ค.

<br>

### 2๏ธโฃ Project Convention

๊ฐ ๋ฉค๋ฒ๋ณ ํ๋ก์ ํธ ๊ตฌ์กฐ๋ ๋ค์๊ณผ ๊ฐ์ต๋๋ค
**ํ๋ก์ ํธ์ด๋ฆ/week๋ฒํธ/ํ๋ซํผ_๋ฌธ์ ๋ฒํธ_๋ ๋ฒจ_๋ฌธ์ ์ด๋ฆ/...**

    jodawoooon/week15/BOJ_1051_S3_์ซ์์ ์ฌ๊ฐํ/...

<br>

### 3๏ธโฃ Commit Convention
ํ๋ฒ์ ๋ชจ๋  ํ์ผ์ addํ์ง ์๊ณ  type๋ณ๋ก ๋ถ๋ฆฌํ์ฌ commit ํฉ๋๋ค.

    docs : README.md ๋ฑ ๋ฌธ์ ์์ฑ ๋ฐ ์์ 
    code : ์ฝ๋ ์์ฑ
    fix : ์ฝ๋ ์์ 
    add : ๊ธฐ์กด์ ํผ ๋ฌธ์ ์ ๋ํ ์ถ๊ฐ
    remove : ์ฝ๋ ๋ฐ ๋ฌธ์ ์ญ์ 
    merge : pr(pull request)์ ํตํด ์์ ์ repo์์ ์๋ณธ repo๋ก mergeํ๊ธฐ
  <br>

์ ์ฉ ์์ ::
1. BOJ์ 1051๋ฒ ์ซ์ ์ ์ฌ๊ฐํ (silver3) ๋ฌธ์ ๋ฅผ ํ์๋ค๋ฉด
ํด๋น ์ฝ๋๋ฅผ ํ๋์ commit์ผ๋ก ๋ถ๋ฆฌํฉ๋๋ค.  
์ด ๋์ commit message๋ ๋ค์๊ณผ ๊ฐ์ด ํต์ผํฉ๋๋ค
		
		 git commit -m "code : BOJ 1051 S3 ์ซ์์ ์ฌ๊ฐํ"

	ํด๋น ์ฝ๋๋ฅผ ์์ ํ  ๋์ commit message๋ ๋ค์๊ณผ ๊ฐ์ด ํต์ผํฉ๋๋ค.
		
		 git commit -m "fix : BOJ 1051 S3 ์ซ์์ ์ฌ๊ฐํ"

2.  ์ฝ๋์ ๋ํ ์ค๋ช์ ์์ฑํ๊ณ 
ํด๋น ๋ฌธ์๋ฅผ ํ๋์ commit์ผ๋ก ๋ถ๋ฆฌํฉ๋๋ค.  
์ด ๋์ commit message๋ ๋ค์๊ณผ ๊ฐ์ต๋๋ค.
		
		 git commit -m "docs : BOJ 1051 S3 ์ซ์์ ์ฌ๊ฐํ"

3. main README.md ํ์ผ์ ์์ ํ  ๋์ commit message๋ ๋ค์๊ณผ ๊ฐ์ต๋๋ค.
		
		 git commit -m "docs : main README update"

5. ํ์ผ์ ์ญ์ ํ  ๊ฒฝ์ฐ commit message๋ ๋ค์๊ณผ ๊ฐ์ต๋๋ค
		
		 git commit -m "remove : ์ญ์ ํ์ผ"
		
<br>

### 4๏ธโฃ Review Convention
1. Pull Request์ ์ ๋ชฉ์ ๋ค์๊ณผ ๊ฐ์ด ํต์ผํฉ๋๋ค.
**์ด๋ฆ : ๋ฌธ์ ํ๋ซํผ ๋ฌธ์ ๋ฒํธ ๋ฌธ์ ๋ฑ๊ธ ๋ฌธ์ ์ ๋ชฉ** 
		
		 DAUN JO : BOJ 1051 S3 ์ซ์์ ์ฌ๊ฐํ
		
2. Pull Request์ comment์๋ ๋ณธ์ธ์ด ์์ฑํ README.md์ ๋ด์ฉ์ ์ถ๊ฐํฉ๋๋ค. 

3. ๋ฌธ์ ์ ํด๋นํ๋ ์ ํ์ ์ ํํ์ฌ PR์ label์ attachํ๊ณ ,   
 ์์ ์ PR์ assignee์ ์์ ์ ์ถ๊ฐ ํ ๋ฌธ์ ํ์ด week์ ํด๋นํ๋ Milestones์ ์ ํํฉ๋๋ค.

4. ๊ธฐ์กด์ PR์ ์์ฑ ํ ์๋ก์ด ๋ฌธ์ ๋ฅผ ํ์์ ๊ฒฝ์ฐ, ์๋ก์ด ๋ฌธ์ ์ ๋ํ commit์ ํ๊ธฐ ์  ๋ค์ ๊ณผ์ ์ ์ํํฉ๋๋ค.

	- โ ์ฝ๋๋ฆฌ๋ทฐ๊ฐ ์๋ฃ ๋์์ ๊ฒฝ์ฐ  
		์์ ์ PR์์ merge ๋ฒํผ์ ๋๋ฌ merge ํฉ๋๋ค. 
		
	- โ ๋ฆฌ๋ทฐ ์๋ฃ ์  ์๋ก์ด ๋ฌธ์ ๋ฅผ ํ ๊ฒฝ์ฐ
		1. ์์ ์ local์์ ์๋ก ํผ ๋ฌธ์ ์ ๋ํ branch๋ฅผ ์์ฑํฉ๋๋ค.  
		์ด ๋ branch์ ์ด๋ฆ์ **๋ฌธ์ ํ๋ซํผ-๋ฌธ์ ๋ฒํธ**๊ณผ ๊ฐ์ด ์์ฑํ๋ ๊ฒ์ ๊ถ์ฅํฉ๋๋ค.
		
			    boj-1051
		
		2. ์๋ก์ด ๋ฌธ์ ์ ๋ํ code์ README.md์ ๋ํ commit์ ์ถ๊ฐ ํ pushํฉ๋๋ค.   
		์ด ๋์ commit message๋ 2๏ธโฃ Commit Convention์์ ์ธ๊ธํ ๊ท์น์ ๋ง๊ฒ ์ค์ ํฉ๋๋ค.
		3. ์ด ๋ ๋ฐ๋์ (a)์์ ์์ฑํ branch๋ก push ๋๋์ง ํ์ธํฉ๋๋ค.
		4. ๋ณธ์ธ ๊ณ์ ์ fork๋ repo์์ Pull Request์ ์์ฑํ  ๋,   
		์ฝ๋๊ฐ push๋ ๋ธ๋์น(a์์ ์์ฑํ jodawoooon/boj-1051)์์   
		organization repo์ main ๋ธ๋์น๋ก Pull Request๋ฅผ ๋ณด๋๋๋ค.


<br><br>

## ๐ Solved Problems
### ๐ฉ week 1
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 13460 | [๊ตฌ์ฌ ํ์ถ 2](https://www.acmicpc.net/problem/13460) | BFS | gold2 |
| BOJ | 20055 | [์ปจ๋ฒ ์ด์ด ๋ฒจํธ ์์ ๋ก๋ด](https://www.acmicpc.net/problem/20055) | ์๋ฎฌ | silver1 |
| BOJ | 17142 | [์ฐ๊ตฌ์ 3](https://www.acmicpc.net/problem/17142) | BFS | gold4 |
| BOJ | 14891 | [ํฑ๋๋ฐํด](https://www.acmicpc.net/problem/14891) | ์๋ฎฌ| silver1 |



### ๐ฉ week 2
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 2527 | [์ง์ฌ๊ฐํ](https://www.acmicpc.net/problem/2527) | ๊ธฐํํ | silver1 |
| BOJ | 2304 | [์ฐฝ๊ณ  ๋ค๊ฐํ](https://www.acmicpc.net/problem/2304) | ๋ธ๋ฃจํธํฌ์ค| silver2 |
| BOJ | 2116 | [์ฃผ์ฌ์ ์๊ธฐ](https://www.acmicpc.net/problem/2116) | ๋ธ๋ฃจํธํฌ์ค | gold5 |
| BOJ | 2564 | [๊ฒฝ๋น์](https://www.acmicpc.net/problem/2564) | ์๋ฎฌ| silver1 |




### ๐ฉ week 3
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 17281 | [โพ](https://www.acmicpc.net/problem/17281) | ๋ธ๋ฃจํธํฌ์ค| gold4 |
| BOJ | 16953 | [A->B](https://www.acmicpc.net/problem/16953) | DFS | silver1 |
| BOJ | 14503 | [๋ก๋ด์ฒญ์๊ธฐ](https://www.acmicpc.net/problem/14503) | ์๋ฎฌ | gold5 |
| BOJ | 14888 | [์ฐ์ฐ์ ๋ผ์๋ฃ๊ธฐ](https://www.acmicpc.net/problem/14888) | DFS | silver1 |



### ๐ฉ  week 4
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 16637 | [๊ดํธ ์ถ๊ฐํ๊ธฐ](https://www.acmicpc.net/problem/16637) | DFS| gold3 |
| BOJ | 17070 | [ํ์ดํ ์ฎ๊ธฐ๊ธฐ 1](https://www.acmicpc.net/problem/17070) | DFS | gold5 |
| BOJ | 17471 | [๊ฒ๋ฆฌ๋งจ๋๋ง](https://www.acmicpc.net/problem/17471) | BFS| gold5 |
| BOJ | 17472 | [๋ค๋ฆฌ ๋ง๋ค๊ธฐ 2](https://www.acmicpc.net/problem/17472) | BFS| gold2 |


### ๐ฉ  week 5
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 14889 | [์คํํธ์ ๋งํฌ](https://www.acmicpc.net/problem/14889) | comb | silver3 |
| BOJ | 15685 | [๋๋๊ณค ์ปค๋ธ](https://www.acmicpc.net/problem/15685) | ์๋ฎฌ| gold4 |
| BOJ | 16234 | [์ธ๊ตฌ ์ด๋](https://www.acmicpc.net/problem/16234) | BFS| gold5 |
| BOJ | 20056 | [๋ง๋ฒ์ฌ ์์ด์ ํ์ด์ด๋ณผ](https://www.acmicpc.net/problem/20056) | ์๋ฎฌ| gold5 |


### ๐ฉ week 6
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 12763 | [์ง๊ฐํ๋ฉด ์ ๋ผ](https://www.acmicpc.net/problem/12763) | ํ๋ก์ด๋ ์์ฌ | gold2 |
| BOJ | 6497 | [์ ๋ ฅ๋](https://www.acmicpc.net/problem/6497) | ๋ค์ต์คํธ๋ผ | gold4 |
| BOJ | 1238 | [ํํฐ](https://www.acmicpc.net/problem/1238) |ํฌ๋ฃจ์ค์นผ | gold3 |
| BOJ | 9694 | [๋ฌด์์ ์๋๋๊ฐ ์๋๋ผ ๋๊ตฌ๋ฅผ ์๋๋๊ฐ ๋ฌธ์ ๋ค](https://www.acmicpc.net/problem/9694) | ๋ค์ต์คํธ๋ผ| gold4 |


### ๐ฉ week 7
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 17071 | [์จ๋ฐ๊ผญ์ง 5](https://www.acmicpc.net/problem/17071) | BFS | gold1 |
| BOJ | 1242 | [์ํ](https://www.acmicpc.net/problem/1242) | ์ํ | gold2 |
| BOJ | 12904 | [A์ B](https://www.acmicpc.net/problem/12904) | ๋ฌธ์์ด | gold5 |
| BOJ | 16959 | [์ฒด์คํ ์ฌํ 1](https://www.acmicpc.net/problem/16959) | BFS | gold1 |


### ๐ฉ week 8
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 16197 | [๋ ๋์ ](https://www.acmicpc.net/problem/16197) | BFS | gold4 |
| BOJ | 7579 | [์ฑ](https://www.acmicpc.net/problem/7579) | DP | gold3 |
| BOJ | 1062 | [๊ฐ๋ฅด์นจ](https://www.acmicpc.net/problem/1062) | ๋ฌธ์์ด | gold4 |
| BOJ | 2156 | [ํฌ๋์ฃผ ์์](https://www.acmicpc.net/problem/2156) | DP | silver1 |



### ๐ฉ week 9
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 2234 | [์ฑ๊ณฝ](https://www.acmicpc.net/problem/2234) | BFS | gold4 |
| BOJ | 14938 | [์๊ฐ๊ทธ๋ผ์ด๋](https://www.acmicpc.net/problem/14938) | ๊ทธ๋ํ | gold4 |
| BOJ | 17822 | [์ํ ๋๋ฆฌ๊ธฐ](https://www.acmicpc.net/problem/17822) | ์๋ฎฌ | gold3 |
| BOJ | 2565 | [์ ๊น์ค](https://www.acmicpc.net/problem/2565) | DP | gold3 |

### ๐ฉ week 10
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 1030 | [ํ๋ ํ ํ๋ฉด](https://www.acmicpc.net/problem/1030) | ๋ถํ  ์ ๋ณต | gold3 |
| BOJ | 8972 | [๋ฏธ์น ์๋์ด๋ธ](https://www.acmicpc.net/problem/8972) | ์๋ฎฌ | gold4 |
| BOJ | 11967 | [๋ถ์ผ๊ธฐ](https://www.acmicpc.net/problem/11967) | ๊ทธ๋ํ | gold4 |
| BOJ | 14719 | [๋น๋ฌผ](https://www.acmicpc.net/problem/14719) | ๊ตฌํ | gold5 |

### ๐ฉ week 11
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 1915 | [๊ฐ์ฅ ํฐ ์ ์ฌ๊ฐํ](https://www.acmicpc.net/problem/1915) | dp | silver1 |
| BOJ | 13335 | [ํธ๋ญ](https://www.acmicpc.net/problem/13335) | ์๋ฎฌ | silver1 |
| BOJ | 3709 | [๋ ์ด์ ๋น์ ์ด๋๋ก](https://www.acmicpc.net/problem/1915) | dfs | gold4 |
| BOJ | 6087 | [๋ ์ด์ ํต์ ](https://www.acmicpc.net/problem/6087) | bfs | gold4 |

### ๐ฉ week 12
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 12608 | [์์ด ์ด๋ฑํ๊ต](https://www.acmicpc.net/problem/12608) | ์๋ฎฌ | silver1 |
| BOJ | 10836 | [์ฌ์๋ฒ](https://www.acmicpc.net/problem/10836) | ์๋ฎฌ | gold4 |
| BOJ | 1520 | [๋ด๋ฆฌ๋ง๊ธธ](https://www.acmicpc.net/problem/1520) | dp | gold4 |
| BOJ | 11559 | [Puyo Puyo](https://www.acmicpc.net/problem/11559) | ์๋ฎฌ | gold5 |

### ๐ฉ week 13
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 14499 | [์ฃผ์ฌ์ ๊ตด๋ฆฌ๊ธฐ](https://www.acmicpc.net/problem/14499) | ์๋ฎฌ | gold5 |
| BOJ | 15787 | [๊ธฐ์ฐจ๊ฐ ์ด๋ ์ ํค์น๊ณ  ์ํ์๋ฅผ](https://www.acmicpc.net/problem/15787) | ๋นํธ๋ง์คํน | silver2 |
| BOJ | 19238 | [์คํํธํ์](https://www.acmicpc.net/problem/19238) | bfs | gold4 |
| BOJ | 2878 | [์บ๋์บ๋](https://www.acmicpc.net/problem/2878) | ๊ทธ๋ฆฌ๋ | gold2 |

### ๐ฉ week 14
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 5014 | [์คํํธ๋งํฌ](https://www.acmicpc.net/problem/5014) | bfs | gold5 |
| BOJ | 9935 | [๋ฌธ์์ด ํญ๋ฐ](https://www.acmicpc.net/problem/9935) | ๋ฌธ์์ด | gold4 |


### ๐ฉ week 15 
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 1051 | [์ซ์ ์ ์ฌ๊ฐํ](https://www.acmicpc.net/problem/1051) | ๊ตฌํ | silver3 |
| BOJ | 1292 | [์ฝ๊ฒ ํธ๋ ๋ฌธ์ ](https://www.acmicpc.net/problem/1292) | ๊ตฌํ | silver5 |
| BOJ | 1934 | [์ต์๊ณต๋ฐฐ์](https://www.acmicpc.net/problem/1934) | ์ํ | silver5 |
| BOJ | 2960 | [์๋ผํ ์คํ๋ค์ค์ ์ฒด](https://www.acmicpc.net/problem/2960) | ์ํ | silver4 |
| BOJ | 3085 | [์ฌํ ๊ฒ์](https://www.acmicpc.net/problem/3085) | ๊ตฌํ | silver4 |
| BOJ | 10773 | [์ ๋ก](https://www.acmicpc.net/problem/10773) | ๊ตฌํ | silver4 |
| BOJ | 10870 | [ํผ๋ณด๋์น ์ 5](https://www.acmicpc.net/problem/10870) | ์ํ | bronze2 |
| BOJ | 11068 | [ํ๋ฌธ์ธ ์](https://www.acmicpc.net/problem/11068) | ์ํ | silver5 |
| BOJ | 7568 | [๋ฉ์น](https://www.acmicpc.net/problem/7568) | ๊ตฌํ | silver5 |
| BOJ | 1157 | [๋จ์ด ๊ณต๋ถ](https://www.acmicpc.net/problem/1157) | ๊ตฌํ | bronze1 |
| BOJ | 2869 | [๋ฌํฝ์ด๋ ์ฌ๋ผ๊ฐ๊ณ  ์ถ๋ค](https://www.acmicpc.net/problem/2869) | ์ํ | bronze1 |
| BOJ | 14646 | [์ฑ์ ๋ ๊ฒฐ์ ์ฅ์ ์ผ!!](https://www.acmicpc.net/problem/14646) | ๊ตฌํ | silver4 |


### ๐ฉ week 16
| Type | ๋ฌธ์  | ์ ๋ชฉ | ์ ํ | rank |
| -- |--| -- |--|--|
| BOJ | 10546 | [๋ฐฐ๋ถ๋ฅธ ๋ง๋ผํ ๋](https://www.acmicpc.net/problem/10546) | ์๋ฃ๊ตฌ์กฐ | silver4 |
| BOJ | 1302 | [๋ฒ ์คํธ์๋ฌ](https://www.acmicpc.net/problem/1302) | ์๋ฃ๊ตฌ์กฐ | silver4 |
| BOJ | 1927 | [์ต์ ํ](https://www.acmicpc.net/problem/1927) | ์๋ฃ๊ตฌ์กฐ | silver1 |
| BOJ | 2164 | [์นด๋2](https://www.acmicpc.net/problem/2164) | ์๋ฃ๊ตฌ์กฐ | silver4 |
| BOJ | 2910 | [๋น๋ ์ ๋ ฌ](https://www.acmicpc.net/problem/2910) | ์๋ฃ๊ตฌ์กฐ | silver3 |
| BOJ | 10799 | [์ ๋ง๋๊ธฐ](https://www.acmicpc.net/problem/10799) | ์๋ฃ๊ตฌ์กฐ | silver3 |
| BOJ | 17479 | [์ ์๋น](https://www.acmicpc.net/problem/17479) | ์๋ฃ๊ตฌ์กฐ | silver3 |
| BOJ | 20301 | [๋ฐ์  ์์ธํธ์ค](https://www.acmicpc.net/problem/20301) | ์๋ฃ๊ตฌ์กฐ | silver4 |
| BOJ | 1417 | [๊ตญํ์์ ์ ๊ฑฐ](https://www.acmicpc.net/problem/1417) | ์๋ฃ๊ตฌ์กฐ | silver5 |
| BOJ | 1764 | [๋ฃ๋ณด์ก](https://www.acmicpc.net/problem/1764) | ์๋ฃ๊ตฌ์กฐ | silver4 |
| BOJ | 7785 | [ํ์ฌ์ ์๋ ์ฌ๋](https://www.acmicpc.net/problem/7785) | ์๋ฃ๊ตฌ์กฐ | silver5 |
| BOJ | 12019 | [Yonsei TOTO](https://www.acmicpc.net/problem/12018) | ์๋ฃ๊ตฌ์กฐ | silver3 |


### ๐ฉ week 17
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| Programmers | [K๋ฒ์งธ์](https://programmers.co.kr/learn/courses/30/lessons/42748) | ์ ๋ ฌ | level1 |
| Programmers | [๊ฐ์ฅ ํฐ ์](https://programmers.co.kr/learn/courses/30/lessons/42746) | ์ ๋ ฌ | level2 |
| Programmers | [H-Index](https://programmers.co.kr/learn/courses/30/lessons/42747) | ์ ๋ ฌ | level2 |
| Programmers | [๋ชจ์๊ณ ์ฌ](https://programmers.co.kr/learn/courses/30/lessons/42840) | ์ํ | level1 |
| Programmers | [์์์ฐพ๊ธฐ](https://programmers.co.kr/learn/courses/30/lessons/42839) | ์ํ | level2 |
| Programmers | [์นดํซ](https://programmers.co.kr/learn/courses/30/lessons/42842) | ์ํ | level2 |


### ๐ฉ week 18
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| Programmers | [ํ๊ฒ ๋๋ฒ](https://programmers.co.kr/learn/courses/30/lessons/43165) | DFS/BFS | level2 |
| Programmers | [๋คํธ์ํฌ](https://programmers.co.kr/learn/courses/30/lessons/43162) | DFS/BFS | level3 |
| Programmers | [๋จ์ด ๋ณํ](https://programmers.co.kr/learn/courses/30/lessons/43163) | DFS/BFS | level3 |
| Programmers | [์ฌํ๊ฒฝ๋ก](https://programmers.co.kr/learn/courses/30/lessons/43164) | DFS/BFS | level3 |
| Programmers | [์๊ตญ์ฌ์ฌ](https://programmers.co.kr/learn/courses/30/lessons/43238) | ์ด๋ถํ์ | level3 |
| Programmers | [์ง๊ฒ๋ค๋ฆฌ](https://programmers.co.kr/learn/courses/30/lessons/43236) | ์ด๋ถํ์ | level4 |

### ๐ฉ week 19
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| Programmers | [๊ฐ์ฅ ๋จผ ๋ธ๋](https://programmers.co.kr/learn/courses/30/lessons/49189) | ๊ทธ๋ํ | level3 |
| Programmers | [์์](https://programmers.co.kr/learn/courses/30/lessons/49191) | ๊ทธ๋ํ | level3 |
| Programmers | [๋ฐฉ์ ๊ฐ์](https://programmers.co.kr/learn/courses/30/lessons/49190) | ๊ทธ๋ํ | level5 |
| Programmers | [๋ ๋งต๊ฒ](https://programmers.co.kr/learn/courses/30/lessons/42626) | ํ | level2 |
| Programmers | [๋์คํฌ ์ปจํธ๋กค๋ฌ](https://programmers.co.kr/learn/courses/30/lessons/42627) | ํ | level3 |
| Programmers | [์ด์ค์ฐ์ ์์ํ](https://programmers.co.kr/learn/courses/30/lessons/42628) | ํ | level3 |

### ๐ฉ week 20
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| Programmers | [์์ฃผํ์ง ๋ชปํ ์ ์](https://programmers.co.kr/learn/courses/30/lessons/42576) | ํด์ | level1 |
| Programmers | [์ ํ๋ฒํธ ๋ชฉ๋ก](https://programmers.co.kr/learn/courses/30/lessons/42577) | ํด์ | level2 |
| Programmers | [์์ฅ](https://programmers.co.kr/learn/courses/30/lessons/42578) | ํด์ | level2 |
| Programmers | [๋ฒ ์คํธ์จ๋ฒ](https://programmers.co.kr/learn/courses/30/lessons/42579) | ํด์ | level3 |
| Programmers | [N ์ผ๋กํํ](https://programmers.co.kr/learn/courses/30/lessons/42895) | DP | level3 |
| Programmers | [์ ์ ์ผ๊ฐํ](https://programmers.co.kr/learn/courses/30/lessons/43105) | DP | level3 |

### ๐ฉ week 21
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| Programmers | [๊ธฐ๋ฅ๊ฐ๋ฐ](https://programmers.co.kr/learn/courses/30/lessons/42586) | ์คํ/ํ | level2 |
| Programmers | [ํ๋ฆฐํฐ](https://programmers.co.kr/learn/courses/30/lessons/42587) | ์คํ/ํ | level2 |
| Programmers | [๋ค๋ฆฌ๋ฅผ ์ง๋๋ ํธ๋ญ](https://programmers.co.kr/learn/courses/30/lessons/42583) | ์คํ/ํ | level2 |
| Programmers | [์ฃผ์๊ฐ๊ฒฉ](https://programmers.co.kr/learn/courses/30/lessons/42584) | ์คํ/ํ | level2 |
| Programmers | [๋ฑ๊ตฃ๊ธธ](https://programmers.co.kr/learn/courses/30/lessons/42898) | DP | level3 |
| Programmers | [๋๋์ง](https://programmers.co.kr/learn/courses/30/lessons/42897) | DP | level4 |

### ๐ฉ week 22
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| BOJ | [๋์  ์๋ฅด๊ธฐ](https://www.acmicpc.net/problem/1654) | ์ด๋ถ ํ์ | silver3 |
| BOJ | [๋๋ฌด ์๋ฅด๊ธฐ](https://www.acmicpc.net/problem/2805) | ์ด๋ถ ํ์ | silver3 |
| BOJ | [๊ฐ์ฅ ๊ธด ์ฆ๊ฐํ๋ ๋ถ๋ถ ์์ด 2](https://www.acmicpc.net/problem/12015) | ์ด๋ถ ํ์ | gold2 |
| BOJ | [๊ณต์ ๊ธฐ ์ค์น](https://www.acmicpc.net/problem/2110) | ์ด๋ถ ํ์ | silver1 |

### ๐ฉ week 23
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| BOJ | [ํธ๋ฆฌ](https://www.acmicpc.net/problem/1068) | ํธ๋ฆฌ | gold5 |
| BOJ | [์ ํ๋ฒํธ ๋ชฉ๋ก](https://www.acmicpc.net/problem/5052) | ํธ๋ฆฌ | gold4 |
| BOJ | [์ด์ง ๊ฒ์ ํธ๋ฆฌ](https://www.acmicpc.net/problem/5639) | ํธ๋ฆฌ | silver1 |
| BOJ | [์ฌ์ด](https://www.acmicpc.net/problem/9489) | ํธ๋ฆฌ | gold4 |

### ๐ฉ week 24
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| BOJ | [๋ฌธ์ ํด๋](https://www.acmicpc.net/problem/1593) | ์ฌ๋ผ์ด๋ฉ ์๋์ฐ | gold4 |
| BOJ | [N๋ฒ์งธ ํฐ ์](https://www.acmicpc.net/problem/2075) | ์ฌ๋ผ์ด๋ฉ ์๋์ฐ | gold5 |
| BOJ | [๋ด๋ ค๊ฐ๊ธฐ](https://www.acmicpc.net/problem/2096) | ์ฌ๋ผ์ด๋ฉ ์๋์ฐ | gold4 |
| BOJ | [ํ์ ](https://www.acmicpc.net/problem/2428) | ์ฌ๋ผ์ด๋ฉ ์๋์ฐ | silver3 |

### ๐ฉ week 25
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| BOJ | [์ต์ ์คํจ๋ ํธ๋ฆฌ](https://www.acmicpc.net/problem/1197) | MST | gold4 |
| BOJ | [๋์ ๋ถํ  ๊ณํ](https://www.acmicpc.net/problem/1647) | MST | gold4 |
| BOJ | [ํ์ฑ ์ฐ๊ฒฐ](https://www.acmicpc.net/problem/16398) | MST | gold4 |
| BOJ | [๋คํธ์ํฌ ์ฐ๊ฒฐ](https://www.acmicpc.net/problem/1922) | MST | gold4 |

### ๐ฉ week 26
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| Programmers | [๊ฒฝ์ฃผ๋ก ๊ฑด์ค](https://programmers.co.kr/learn/courses/30/lessons/67259) | ์ต๋จ๊ฒฝ๋ก | - |
| BOJ | [ํน์ ํ ์ต๋จ ๊ฒฝ๋ก](https://www.acmicpc.net/problem/1504) | ์ต๋จ๊ฒฝ๋ก | gold4 |
| Programmers | [ํฉ์น ํ์ ์๊ธ](https://programmers.co.kr/learn/courses/30/lessons/72413) | ์ต๋จ๊ฒฝ๋ก | Lv3 |
| Programmers | [๋ฐฐ๋ฌ](https://programmers.co.kr/learn/courses/30/lessons/12978?language=java) | ์ต๋จ๊ฒฝ๋ก | - |

### ๐ฉ week 27
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| BOJ | [๋ง๋ฒ์ฌ์์ด์ ๋น๋ฐ๋ผ๊ธฐ](https://www.acmicpc.net/problem/21610) | ๊ตฌํ | gold5 |
| BOJ | [๋ฑ](https://www.acmicpc.net/problem/3190) | ๊ตฌํ | gold5 |
| BOJ | [๊ฒ๋ฆฌ๋งจ๋๋ง 2](https://www.acmicpc.net/problem/17779) | ๊ตฌํ | gold4 |
| BOJ | [ํต๋๋ฌด ์ฎ๊ธฐ๊ธฐ](https://www.acmicpc.net/problem/1938) | ๊ตฌํ |  |


### ๐ฉ week 28
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| BOJ | [๊ฐ์ํ๋ ์](https://www.acmicpc.net/problem/1038) | ๋ฐฑํธ๋ํน | gold5 |
| BOJ | [์ข์์์ด](https://www.acmicpc.net/problem/2661) | ๋ฐฑํธ๋ํน | gold4 |
| BOJ | [ํฉ ๊ตฌํ๊ธฐ](https://www.acmicpc.net/problem/11441) | ๋์ ํฉ | silver3 |
| BOJ | [๋๋จธ์ง ํฉ](https://www.acmicpc.net/problem/10986) | ๋์ ํฉ | gold3 |

### ๐ฉ week 29
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| BOJ | [์ผ๊ทผ ์ง์](https://programmers.co.kr/learn/courses/30/lessons/12927) |  |  |
| BOJ | [๋ฒฝ ๋ถ์๊ณ  ์ด๋ํ๊ธฐ](https://www.acmicpc.net/problem/2206) | BFS | gold4 |
| BOJ | [์์ข์ด ๋ง๋ค๊ธฐ](https://www.acmicpc.net/problem/2630) | ๋ถํ ์ ๋ณต | silver3 |
| BOJ | [์บ ํ๊ฐ๋ ์์](https://www.acmicpc.net/problem/1590) | ๋ธ๋ฃจํธํฌ์ค | silver1 |

### ๐ฉ week 30
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| BOJ | [์ด๋ฅธ ์์ด](https://www.acmicpc.net/problem/19237) | ์๋ฎฌ | gold3 |
| BOJ | [๋ฑ์ฐจ์์ด์ ๊ฐ์](https://www.acmicpc.net/problem/13558) | ์ํ | gold2 |
| BOJ | [๋ง๋ฒ์ฌ ์์ด์ ํ์ด์ด์คํฐ](https://www.acmicpc.net/problem/20058) | ์๋ฎฌ | gold4 |
| BOJ | [ํํธ๋ก๋ฏธ๋ธ](https://www.acmicpc.net/problem/14500) | ๊ตฌํ,๋ธ๋ฃจํธํฌ์ค | gold5 |

### ๐ฉ week 31
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| BOJ | [ํฑํํ ](https://www.acmicpc.net/problem/7682) | ๋ฐฑํธ๋ํน | gold5 |
| BOJ | [์ด์ฐจ์ ๋ฐฐ์ด๊ณผ ์ฐ์ฐ](https://www.acmicpc.net/problem/17140) | ์ ๋ ฌ,์๋ฎฌ | gold4 |
| BOJ | [๋ฏธ์น ๋ก๋ด](https://www.acmicpc.net/problem/1405) | ๋ฐฑํธ๋ํน | gold5 |
| BOJ | [์๋ก์ด ๊ฒ์ 2](https://www.acmicpc.net/problem/17837) | ์๋ฎฌ๋ ์ด์ | gold2 |

### ๐ฉ week 32
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| BOJ | [์ฒญ์๋ ์์ด](https://www.acmicpc.net/problem/19236) | ๋ฐฑํธ๋ํน | gold2 |
| BOJ | [N-Queen](https://www.acmicpc.net/problem/9663) | ๋ฐฑํธ๋ํน | gold5 |
| BOJ | [์ด๋](https://www.acmicpc.net/problem/1956) | ํ๋ก์ด๋โ์์ฌ | gold4 |
| BOJ | [ํ์์ค๋น ](https://www.acmicpc.net/problem/2610) | ํ๋ก์ด๋โ์์ฌ | gold2 |

### ๐ฉ week 33
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| BOJ | [ํธ๋ฆฌ](https://www.acmicpc.net/problem/4256) | ํธ๋ฆฌ,๋ถํ ์ ๋ณต | gold3 |
| BOJ | [์ ์ธ](https://www.acmicpc.net/problem/10159) | ํ๋ก์ด๋-์์ฌ | gold3 |
| BOJ | [์๊ธฐ ์์ด2](https://www.acmicpc.net/problem/17086) | BFS | silver2 |
| BOJ | [๊ฐ์ ํผํ๊ธฐ](https://www.acmicpc.net/problem/18428) | ๋ฐฑํธ๋ํน | silver1 |

### ๐ฉ week 34
| Type | ๋ฌธ์  |  ์ ํ | rank |
| -- | -- |--|--|
| Programmers | [ํค๋น ์ ์ ๊ฐ ์์ ํ ์ฅ์](https://programmers.co.kr/learn/courses/30/lessons/77487) | SQL | LV3 |
| Programmers | [ํ๋ ฌ ํ๋๋ฆฌ ํ์ ํ๊ธฐ](https://programmers.co.kr/learn/courses/30/lessons/77485) | - | LV2 |
| Programmers | [๋ก๋์ ์ต๊ณ  ์์์ ์ต์  ์์](https://programmers.co.kr/learn/courses/30/lessons/77484) | - | LV1 |
| Programmers | [๋ค๋จ๊ณ ์นซ์ ํ๋งค](https://programmers.co.kr/learn/courses/30/lessons/77486) | - | LV3 |
