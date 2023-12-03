# Statistics

<br>
<br>

# 데이터

## 질적 변수 vs 양적 변수

### 질적 변수
> 1. 매우 좋음　　2. 좋음　　3. 보통　　4. 나쁨　　5. 매우 나쁨  
> A형　　B형　　O형　　AB형  

흡연여부, 남성과 여성 같이 값이 2개인 질적 변수는 __2진변수__ 라고 한다. True or False라서 1과 0으로 표현 가능하지만, 질적변수다.

#### __명의 척도__
명의 척도의 목적은 구별하는 것으로, 학생번호나 전화번호, 성별 등이 있다.

#### __순서 척도__
순서 관계나 __대소 관계__ 에 대한 의미만 있을 때. 성적 순위나 설문조사 만족도 등이 있다.  
8등과 4등의 차이가 8등과 12등과의 차이와 같다고 말하기 힘들고, 4등이 8등의 두배라고 하기 힘든 상황의 변수를 말함.

### 양적 변수
> 시험점수, 키

#### __간격 척도__
간격 척도는 대소 관계와 함께 그 __차이__ 에도 의미를 두는 변수. 연도나 온도 등이 있다.  
60도는 30도보다 높은 온도이므로 대소 관계에 의미가 있고 그 차이도 의미가 있다.  
하지만 60도는 30도보다 2배 높은 온도라고 말할 수 없기에 간격 척도다.

#### __비례 척도__
비례 척도는 __대소 관계, 차이, 비__ 모두 의미가 있는 변수. 길이, 무게 등이 있다.  
50cm와 100cm는 2배 차이라고 말할 수 있다.

- 간격 척도와 비례 척도 구분 Tip
    - 0이 없음을 뜻하는지 확인하면 된다.

<br>

## 이산형 변수 vs 연속형 변수
### 이산형 변수
0, 1, 2, 3, ... 같이 하나하나의 값을 취하는 변수.
### 연속형 변수
연속적인 값을 취하기에 두 숫자 사이에도 반드시 숫가가 있음. 계속 쪼개짐.

<br>
<br>
<br>

# 1차원 데이터
```
# 데이터 가져오기
df = pd.read_csv("etc/ch2_scores_em.csv", index_col="student number")
scores = np.array(df["english"])[:10]
scores_df = pd.DataFrame({"score":scores}, index=pd.Index(["A", "B", "C", "D", "E", "F", "G", "H", "I", "J"]), name = "studnet")
```
### 평균값 mean
다 아는 일반적인 평균. 시그마나 엑스바로 표현.
```
np.mean(scores)
score_df.mean()
```


### 중앙값 median
데이터를 크기 순으로 나열했을 때, 정중앙에 위치하는 값을 중앙값이라고 한다.  
중앙값은 평균값에 비해 이상값에 강하다.  
[1, 2, 3, 4, 5, 6, 1000]이 있을 때, 아주 큰 이상값 하나 때문에 평균값은 150이 되는데 이럴 때, 중앙값 4를 쓰는게 바람직할 수 있다.  
데이터가 짝수개일 때는 중앙에 있는 값 두개의 평균값을 중앙값으로 본다.
```
np.median(scores)
scores_df.median()
```


### 최빈값 mode
데이터에서 가장 많이 등장한 값.  
최빈값은 기본적으로 질적 데이터의 대푯값을 구할 때 사용하는 지표다. 시험점수같은 양적 데이터에서 최빈값을 구하는 것은 무의미해지기 쉽상이다.
```
pd.Series([1, 1, 1, 2, 2, 3]).mode()
```

### 분산 variance
__편차 deviation__ 은 각 데이터가 평균으로부터 얼마나 떨어져 있는 지를 보여준다. 이 때, 떨어진 정도는 음수와 양수 모두 가능하다.  
하지만 편차의 대푯값으로 평균을 선택하면 편차 평균 즉, 모든 편차의 합은 0이 된다.  
그래서 서로 다른 데이터더라도 평균만 같으면 두 데이터를 구분하고 분석할 수 없는 상황을 초래한다.<br>  
그 결과 평균에서 각각 10의 거리만큼 떨어진 +10인 값과 -10인 값을 동일한 산포도를 갖고 있다고 취급하자는 발상에서 편차의 제곱 즉, 분산을 정의하게 된다.
```
np.var(scores)
scores_df.var(ddof=0)
# Numpy는 표본분산이 default인 반면, Pandas는 불편분산이 default라 ddof라는 매개변수를 통해 표본분산으로 바꿨다.
```



### 표준편차 standard deviation



### 범위


### 사분위 범위



## 데이터 정규화

### 표준화


### 편찻값


## 1차원 데이터 시각화

### 도수분포표

### 히스토그램


### 상자그림

