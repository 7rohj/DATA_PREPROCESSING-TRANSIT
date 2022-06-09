# .-

![image](https://user-images.githubusercontent.com/99319638/172873299-015f3c23-c2ac-40a9-8d5b-ab431377354e.png)

각각 count 하고 rank(Y/N 구분지어서) 메기고 </br>
rank 가 1 ~ 4인 경우, Y 는 4 ~ 1, N는 -4 ~ -1로 score 부여함 </br>

**[문제]** 그리고 구간별로 sum 집계 해주고 싶었는데 이중 집계는 안된다고 자꾸 경고창 떠서 포기. 😨🥶 </br>
**[해결]** 매개 변수 만들어서 사용자가 직접 입력해주는걸로 함 `OTL` </br>
~다른 방법도 생각해보기~ </br>

구간별로 점수 합 구하고 그 중 가장 큰 값을 이용해서, </br>
tabpy 연결 시키고, 거기에 함수 deploy 해서 실행시킴...! </br>

```
def select_random_value( _arg1, _arg2):
    
    columns = [97.636, 97.953, 98.27, 98.587]
    #list = []
    list2 = [_arg2, _arg2, _arg2, _arg2]
    
    cyclenum = cycle(columns)
    next(cyclenum)   
    
    for i in columns:
        if _arg1 == i:
            try:
                tmp = next(cyclenum)

                temp = np.random.uniform(low=i,high=tmp,size=4).tolist()
                
                product = [x*y for x,y in zip(temp,list2)]
```
코드 일부만 작성 `ㅇ.ㅇ` </br>
 
## ‼ 갑자기 작업하던 태블로 파일이 D2E8DA72 코드 뜨면서 안열리는 경우

중간세이브한 파일도 있었긴했는데 이틀전에 저장해 두었던 파일이였다. </br>
진자 심장 멎는줄 알았는데 </br>

찾아보니 간단한 문제 였다. `매개변수를 완전히 지정 안하고 파일을 꺼버리면` 해당 오류 코드가 발생한다.. ㅠ. </br>
해결 방법은 메모장으로 열어서 `"<agg-type type='none' />"` 코드 삭제해 주면 된다.
