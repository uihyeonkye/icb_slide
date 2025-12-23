
# Penguin Dataset Analysis Report

## Dataset Overview
The Palmer Penguins dataset contains data about penguins from three species: Adelie, Chinstrap, and Gentoo.

### Dataset Info
```
None
```

### Descriptive Statistics
```
       bill_length_mm  bill_depth_mm  flipper_length_mm  body_mass_g
count      333.000000     333.000000         333.000000   333.000000
mean        43.992793      17.164865         200.966967  4207.057057
std          5.468668       1.969235          14.015765   805.215802
min         32.100000      13.100000         172.000000  2700.000000
25%         39.500000      15.600000         190.000000  3550.000000
50%         44.500000      17.300000         197.000000  4050.000000
75%         48.600000      18.700000         213.000000  4775.000000
max         59.600000      21.500000         231.000000  6300.000000
```

### Missing Values
```
species              0
island               0
bill_length_mm       0
bill_depth_mm        0
flipper_length_mm    0
body_mass_g          0
sex                  0
dtype: int64
```

## Visualizations

### 1. 부리 길이 히스토그램
![부리 길이 히스토그램](images/hist_bill_length.png)
**인사이트:** 부리 길이의 분포를 분석하면, Adelie 펭귄이 평균적으로 가장 작은 부리를 가지고 있으며, Gentoo 펭귄이 가장 큰 부리를 가지는 경향이 있습니다. 이는 각 종의 먹이 습관이나 서식지 환경에 따른 적응 차이를 보여줍니다. 예를 들어, Gentoo 펭귄은 더 큰 부리로 물고기를 잡는 데 유리할 수 있습니다.

### 2. 부리 깊이 히스토그램
![부리 깊이 히스토그램](images/hist_bill_depth.png)
**인사이트:** 부리 깊이 분포에서는 Chinstrap 펭귄이 가장 깊은 부리를 가지고 있어, 이는 크릴이나 작은 물고기를 효율적으로 잡는 데 특화된 형태임을 시사합니다. 반면 Adelie와 Gentoo는 상대적으로 얕은 부리를 가지며, 이는 다양한 먹이원을 섭취하는 유연성을 제공할 수 있습니다.

### 3. 날개 길이 히스토그램
![날개 길이 히스토그램](images/hist_flipper_length.png)
**인사이트:** 날개 길이의 분포를 보면, Gentoo 펭귄이 가장 긴 날개를 가지고 있어 수영 속도가 빠를 가능성이 높습니다. 이는 Biscoe 섬의 깊은 바다 환경에 적응한 결과로 보입니다. Adelie와 Chinstrap은 비슷한 날개 길이를 가지며, Dream 섬의 얕은 바다에서 활동하는 데 적합합니다.

### 4. 체중 히스토그램
![체중 히스토그램](images/hist_body_mass.png)
**인사이트:** 체중 분포에서는 Gentoo 펭귄이 평균적으로 가장 무겁고, Adelie가 가장 가볍습니다. 이는 체형 차이와 관련이 있으며, Gentoo의 큰 체중은 더 많은 지방 저장과 긴 수영 거리를 지원합니다. 성별 차이도 고려하면, 수컷이 암컷보다 무거운 경향이 있습니다.

### 5. 종별 부리 길이 박스플롯
![종별 부리 길이 박스플롯](images/box_bill_length_species.png)
**인사이트:** 종별 부리 길이 박스플롯에서 Gentoo의 부리가 가장 길고, Adelie가 가장 짧습니다. 분산을 보면 Gentoo가 가장 일관된 부리 길이를 가지며, 이는 종의 안정적인 진화를 나타냅니다. 이상치들은 개체 차이나 측정 오류를 시사할 수 있습니다.

### 6. 종별 부리 깊이 박스플롯
![종별 부리 깊이 박스플롯](images/box_bill_depth_species.png)
**인사이트:** 부리 깊이 박스플롯에서는 Chinstrap이 가장 깊은 부리를 가지며, 이는 크릴 중심의 식단을 반영합니다. Gentoo는 가장 얕은 부리를 가지며, 이는 다양한 먹이원을 섭취하는 전략입니다. 박스의 범위가 좁은 것은 종 내 일관성을 보여줍니다.

### 7. 부리 길이 vs 부리 깊이 산점도
![부리 길이 vs 부리 깊이 산점도](images/scatter_bill_length_depth.png)
**인사이트:** 산점도에서 부리 길이와 깊이의 관계를 보면, Gentoo는 길고 얕은 부리, Chinstrap은 짧고 깊은 부리를 가집니다. 이는 각 종의 먹이 전략을 시각화하며, 클러스터링이 명확하여 종 분류에 유용합니다. 상관관계는 약하지만 의미 있습니다.

### 8. 날개 길이 vs 체중 산점도
![날개 길이 vs 체중 산점도](images/scatter_flipper_mass.png)
**인사이트:** 날개 길이와 체중의 산점도는 강한 양의 상관관계를 보여, 큰 펭귄이 더 긴 날개를 가집니다. Gentoo가 우상단에 위치하며, 이는 효율적인 수영을 위한 진화입니다. 성별 차이도 보이지만, 종 차이가 더 두드러집니다.

### 9. 종별 개수 막대그래프
![종별 개수 막대그래프](images/bar_species_count.png)
**인사이트:** 종별 개수 막대그래프에서 Gentoo가 가장 많고, Adelie와 Chinstrap이 비슷합니다. 이는 섬별 서식지 분포를 반영하며, Biscoe 섬의 Gentoo가 많습니다. 데이터 불균형은 분석 시 고려해야 합니다.

#### Cross-tabulation (Species vs Island)
```
island     Biscoe  Dream  Torgersen
species                            
Adelie         44     55         47
Chinstrap       0     68          0
Gentoo        119      0          0
```
**인사이트:** 교차표에서 Gentoo는 Biscoe 섬에만 서식하고, Chinstrap은 Dream 섬에 집중되어 있습니다. Adelie는 모든 섬에 분포되어 있어 가장 적응력이 높습니다. 이는 섬의 환경 차이(깊이, 먹이원)가 종 분포를 결정짓는 요인임을 보여줍니다.

#### Pivot Table (Mean Body Mass by Species and Sex)
```
sex             Female         Male
species                            
Adelie     3368.835616  4043.493151
Chinstrap  3527.205882  3938.970588
Gentoo     4679.741379  5484.836066
```
**인사이트:** 피봇테이블에서 수컷이 암컷보다 평균 체중이 높으며, Gentoo의 차이가 가장 큽니다. 이는 성적 이형성으로, 수컷이 더 큰 체형을 가집니다. 종별로는 Gentoo가 가장 무겁고, 이는 영양 상태나 서식지 풍부함을 반영할 수 있습니다.

### 10. 종별 체중 바이올린 플롯
![종별 체중 바이올린 플롯](images/violin_body_mass_species.png)
**인사이트:** 바이올린 플롯에서 Gentoo의 체중 분포가 넓고, 평균이 높습니다. Chinstrap은 좁은 분포를 가지며, 이는 서식지 안정성을 시사합니다. 성별 차이를 고려하면, 수컷의 분포가 더 넓어 다양성을 보여줍니다.

### 11. 페어 플롯
![페어 플롯](images/pairplot.png)
**인사이트:** 페어 플롯은 모든 변수 간 관계를 보여, Gentoo가 큰 체형을 가짐을 확인합니다. 대각선 히스토그램은 정규 분포를 띠며, 산점도는 상관관계를 시각화합니다. 이는 종 분류와 회귀 분석에 유용합니다.

### 12. 상관관계 히트맵
![상관관계 히트맵](images/heatmap_corr.png)
**인사이트:** 히트맵에서 날개 길이와 체중의 상관계수가 높아, 큰 펭귄이 긴 날개를 가집니다. 부리 길이와 깊이는 약한 상관관계를 가지며, 이는 독립적인 특징임을 시사합니다. 이는 다중공선성을 피하기 위한 변수 선택에 도움이 됩니다.

## Analysis Summary
- The dataset has 333 penguins after dropping missing values.
- Species distribution: {'Adelie': 146, 'Gentoo': 119, 'Chinstrap': 68}
- Correlations show relationships between physical measurements.
