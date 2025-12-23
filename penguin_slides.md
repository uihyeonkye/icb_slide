# 펭귄 데이터셋 분석 보고서

## 발표자: GitHub Copilot

### 날짜: 2025년 12월 23일

---

# 데이터셋 개요

Palmer Penguins 데이터셋은 남극 펭귄 3종(Adelie, Chinstrap, Gentoo)에 대한 데이터입니다.

- **총 샘플 수**: 344개 (결측치 제거 후 333개)
- **특징**: 종, 섬, 부리 길이/깊이, 날개 길이, 체중, 성별
- **목적**: 종별 차이 분석 및 시각화

---

# 데이터셋 정보

```
<class 'pandas.core.frame.DataFrame'>
Index: 333 entries, 0 to 343
Data columns (total 7 columns):
 #   Column             Non-Null Count  Dtype
---  ------             --------------  -----
 0   species            333 non-null    object
 1   island             333 non-null    object
 2   bill_length_mm     333 non-null    float64
 3   bill_depth_mm      333 non-null    float64
 4   flipper_length_mm  333 non-null    float64
 5   body_mass_g        333 non-null    float64
 6   sex                333 non-null    object
dtypes: float64(4), object(3)
memory usage: 20.8+ KB
```

---

# 기술 통계

| 특징             | 평균     | 표준편차 | 최소 | 최대 |
|------------------|----------|----------|------|------|
| bill_length_mm   | 43.99   | 5.47    | 32.1| 59.6|
| bill_depth_mm    | 17.16   | 1.97    | 13.1| 21.5|
| flipper_length_mm| 200.97  | 14.02   | 172 | 231 |
| body_mass_g      | 4207.06 | 805.22  | 2700| 6300|

---

# 결측치 정보

- species: 0
- island: 0
- bill_length_mm: 0 (원래 2)
- bill_depth_mm: 0 (원래 2)
- flipper_length_mm: 0 (원래 2)
- body_mass_g: 0 (원래 2)
- sex: 0 (원래 11)

결측치는 제거되었습니다.

---

# 시각화 1: 부리 길이 히스토그램

![부리 길이 히스토그램](images/hist_bill_length.png)

**인사이트:** Adelie 펭귄이 가장 작은 부리를 가지고 있으며, Gentoo가 가장 큽니다. 이는 먹이 습관 차이를 반영합니다.

---

# 시각화 2: 부리 깊이 히스토그램

![부리 깊이 히스토그램](images/hist_bill_depth.png)

**인사이트:** Chinstrap이 가장 깊은 부리를 가지며, 크릴 잡기에 특화되어 있습니다.

---

# 시각화 3: 날개 길이 히스토그램

![날개 길이 히스토그램](images/hist_flipper_length.png)

**인사이트:** Gentoo의 날개가 가장 길어 수영에 유리합니다.

---

# 시각화 4: 체중 히스토그램

![체중 히스토그램](images/hist_body_mass.png)

**인사이트:** Gentoo가 가장 무겁고, 수컷이 암컷보다 무겁습니다.

---

# 시각화 5: 종별 부리 길이 박스플롯

![종별 부리 길이 박스플롯](images/box_bill_length_species.png)

**인사이트:** Gentoo의 부리가 가장 길고 일관적입니다.

---

# 시각화 6: 종별 부리 깊이 박스플롯

![종별 부리 깊이 박스플롯](images/box_bill_depth_species.png)

**인사이트:** Chinstrap이 가장 깊고, Gentoo가 얕습니다.

---

# 시각화 7: 부리 길이 vs 깊이 산점도

![부리 길이 vs 부리 깊이 산점도](images/scatter_bill_length_depth.png)

**인사이트:** 종별 클러스터링이 명확합니다.

---

# 시각화 8: 날개 길이 vs 체중 산점도

![날개 길이 vs 체중 산점도](images/scatter_flipper_mass.png)

**인사이트:** 강한 양의 상관관계가 있습니다.

---

# 시각화 9: 종별 개수 막대그래프

![종별 개수 막대그래프](images/bar_species_count.png)

**인사이트:** Gentoo가 가장 많고, 섬별 분포 차이가 있습니다.

---

# 교차표: 종 vs 섬

| island     | Biscoe | Dream | Torgersen |
|------------|--------|-------|-----------|
| Adelie     | 44     | 55    | 47        |
| Chinstrap  | 0      | 68    | 0         |
| Gentoo     | 119    | 0     | 0         |

**인사이트:** 각 종이 특정 섬에 집중되어 있습니다.

---

# 피봇테이블: 평균 체중 (종 x 성별)

| species   | Female | Male  |
|-----------|--------|-------|
| Adelie    | 3369   | 4043  |
| Chinstrap | 3528   | 3939  |
| Gentoo    | 4680   | 5485  |

**인사이트:** 수컷이 암컷보다 무겁고, Gentoo 차이가 큽니다.

---

# 시각화 10: 종별 체중 바이올린 플롯

![종별 체중 바이올린 플롯](images/violin_body_mass_species.png)

**인사이트:** Gentoo 분포가 넓고 평균 높습니다.

---

# 시각화 11: 페어 플롯

![페어 플롯](images/pairplot.png)

**인사이트:** 변수 간 관계를 종별로 보여줍니다.

---

# 시각화 12: 상관관계 히트맵

![상관관계 히트맵](images/heatmap_corr.png)

**인사이트:** 날개 길이와 체중의 상관계수가 높습니다.

---

# 분석 요약

- 데이터셋: 333개 샘플, 3종 펭귄
- 주요 차이: Gentoo가 크고 무거움
- 인사이트: 서식지와 먹이에 따른 적응

---

# 결론

펭귄 데이터 분석을 통해 종별 차이를 이해했습니다. 추가 연구로 생태계 보존에 기여할 수 있습니다.

---

# Q&A

질문 있으신가요?