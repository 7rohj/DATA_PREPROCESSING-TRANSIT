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
 
끄읏
