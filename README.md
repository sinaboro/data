# 📊 DATA — 머신러닝 / 딥러닝 실습 데이터 모음

파이썬 기초, 데이터 분석, 통계, 머신러닝, 딥러닝 강의에서 사용하는 실습용 데이터셋 저장소입니다.

## 🔗 사용 방법

clone하지 않아도 **raw URL**로 바로 읽을 수 있습니다.

```python
import pandas as pd

BASE = "https://raw.githubusercontent.com/sinaboro/data/main/"

iris    = pd.read_csv(BASE + "iris.csv")
titanic = pd.read_csv(BASE + "titanic.csv")
orders  = pd.read_csv(BASE + "orders.tsv", sep="\t")
nsmc    = pd.read_csv(BASE + "ratings_train.txt", sep="\t")
seoul   = pd.read_excel(BASE + "seoulPopulation.xlsx")
```

zip 파일은 받아서 압축을 푼 뒤 사용하세요.

```python
!wget -q https://raw.githubusercontent.com/sinaboro/data/main/dogs_and_cats_small.zip
!unzip -q dogs_and_cats_small.zip
```

> 전체 저장소가 약 1.6GB입니다. 필요한 파일만 받아 쓰는 걸 권장합니다.

---

## 📁 데이터 목록

### 1. 통계 · 기초 분석
| 파일 | 주요 컬럼 | 용도 |
|---|---|---|
| `AGE.csv` | group, sex, score, age | 집단 비교, t-검정 |
| `PlantGrowth.csv` | weight, group | 분산분석(ANOVA) |
| `poisons.csv` | time, poison, treat | 이원 분산분석 |
| `babyboom.csv` | time, gender, weight, minutes | 분포, 포아송·지수분포 |
| `foodWeight.csv` | weight | 단일 표본 검정 |
| `housetasks.csv` | 집안일 × (Wife, Alternating, Husband, Jointly) | 교차표, 카이제곱 검정 |
| `Galton.txt` | Family, Father, Mother, Gender, Height, Kids | 골턴 키 데이터, 회귀의 시작 |
| `PTC.csv` | month, pm10, ta | 미세먼지 상관분석 |
| `salary.csv` | 연령, 월급여액, 연간특별급여액, 근로시간, 근로자수, 경력구분, 성별 | 임금 통계 분석 |

### 2. 회귀 (Regression)
| 파일 | 주요 컬럼 / 타깃 | 용도 |
|---|---|---|
| `boston.csv` | CRIM, RM, LSTAT … → **PRICE** | 보스턴 집값 예측 |
| `house_price.csv` | neighborhood, area, bedrooms, style → **price** | 주택 가격 회귀 |
| `Kaggle_House_Price.csv` | 79개 특성 → **SalePrice** | Kaggle 집값 예측 (특성 공학) |
| `Insurance.csv` | age, sex, bmi, children, smoker, region → **expenses** | 의료비 예측 |
| `Cars.csv` | cylinders, horsepower, weight … → **mpg** | 자동차 연비 예측 |
| `Electric.csv` | compactness, surface_area … → **electricity** | 건물 에너지 사용량 예측 |
| `Bike_Sharing_Demand.csv` | datetime, season, weather, temp … → **count** | 자전거 대여 수요 예측 (Kaggle) |
| `Model_Validation.csv`, `testData.csv` | inputs, outputs | 과대적합·모델 검증 실습 |

### 3. 분류 (Classification)
| 파일 | 주요 컬럼 / 타깃 | 용도 |
|---|---|---|
| `iris.csv` | sepal·petal 길이/너비 → **species** | 붓꽃 다중 분류 |
| `titanic.csv` | pclass, sex, age, fare … → **survived** | 타이타닉 생존 예측 |
| `Default.csv` | student, balance, income → **default** | 신용 부도 예측, 로지스틱 회귀 |
| `creditCardFraud.zip` | `creditcard.csv` | 신용카드 사기 탐지 (불균형 데이터) |
| `Kaggle_Customer_Satisfaction.zip` | `Kaggle_Customer_Satisfaction.csv` | 산탄데르 고객 만족 예측 |
| `mnist_32.csv` | 32개 수치 특성 (0~31), MNIST 축소 데이터 | 차원 축소, 군집·분류 |

### 4. 시계열
| 파일 | 주요 컬럼 | 용도 |
|---|---|---|
| `Seoul_Temp.csv` | date, avg, min, max | 서울 기온 시계열 |
| `TS.csv` | Date, Cases_Guinea, Cases_Liberia | 에볼라 확진자 시계열 |
| `product.csv` | Date, meanPriceEach, totalOrder, customerType … | 판매량 추세 분석 |

### 5. 데이터 전처리 · pandas
| 파일 | 내용 | 용도 |
|---|---|---|
| `orders.tsv` | Chipotle 주문 내역 (order_id, item_name, item_price) | 탭 구분 파일, 문자열 가격 정제, groupby |
| `Online_Retail.zip` | `Online_Retail.xlsx` | 온라인 소매 거래, RFM·고객 세분화 |
| `seoulCCTV.csv` | 자치구별 CCTV 설치 현황 | 데이터 병합, 시각화 |
| `seoulPopulation.xls` / `.xlsx` | 서울시 인구 | 엑셀 읽기, CCTV 데이터와 merge |
| `seoulExpense.csv` | 서울시 업무추진비 집행 내역 (약 70MB) | 대용량 데이터 집계 |
| `notExercise.xls` / `.xlsx` | 엑셀 실습용 데이터 | 엑셀 입출력 (xls·xlsx 비교) |
| `PII.csv` / `PII.xlsx` | 이름, 성별, 나이, 혈액형, 키, 몸무게 (가상 데이터) | 기초 pandas, 비식별화 실습 |

### 6. 추천 시스템 (MovieLens · TMDB)
| 파일 | 주요 컬럼 | 용도 |
|---|---|---|
| `movies.csv` | movieId, title, genres | 영화 정보 |
| `ratings.csv` | userId, movieId, rating, timestamp | 협업 필터링 |
| `tags.csv` | userId, movieId, tag | 태그 기반 추천 |
| `links.csv` | movieId, imdbId, tmdbId | 외부 ID 연결 |
| `tmdb_5000_movies.csv` | genres, keywords, overview, vote_average … | 콘텐츠 기반 추천 |

### 7. 자연어 처리 (NLP)
| 파일 | 내용 | 용도 |
|---|---|---|
| `ratings_train.txt` / `ratings_test.txt` | 네이버 영화 리뷰 (id, document, label) | 한국어 감성 분석 (NSMC, 탭 구분) |
| `naverMovie.csv` | 네이버 영화 리뷰 (id, document, label) | 감성 분석 (CSV 버전) |
| `IMDB.zip` | `aclImdb/` 영어 영화 리뷰 | 영어 감성 분석 |
| `glove.6B.50d.zip` | `glove.6B.50d.txt` (50차원) | 사전학습 단어 임베딩 (GloVe) |
| `ko_w2v.zip` | `ko.bin` | 한국어 Word2Vec 사전학습 모델 |

### 8. 컴퓨터 비전 (CNN)
| 파일 | 내용 | 용도 |
|---|---|---|
| `dogs_and_cats_small.zip` | train·test 등 × cats/dogs 폴더 구조 | 개·고양이 이진 분류 |
| `002_dogs_and_cats_small.h5` | 위 데이터로 학습한 Keras 모델 | 모델 로드, 전이학습, 시각화 |
| `Logo_Data.zip` | 브랜드 로고 이미지 (예: Adidas) | 로고 다중 분류 |
| `Camel.zip` | `Camel.npy` | 넘파이 배열(.npy) 이미지 데이터 |
| `Face.zip` | `Face.npy` | 넘파이 배열(.npy) 이미지 데이터 |
| `maskdataset_2C.zip` | 마스크 착용 2클래스 | 마스크 착용 분류 |
| `animals_part.*` | `animals/` 동물 이미지 (**분할 압축**) | 동물 이미지 분류 |
| `maskdataset_3C_Part.*` | `maskdataset_3C/` 3클래스 (**분할 압축**) | 마스크 착용 3클래스 분류 |
| `maskdataset_3C.tara*` | `yolo_custom_modeling/` (**분할 tar**) | YOLO 커스텀 객체 탐지 |

### 9. 이미지 · 영상 샘플
| 파일 | 용도 |
|---|---|
| `cat.1700.jpg`, `face_07.jpg`, `popova.jpg`, `portrait.png`, `testImage.jpeg` | 학습한 모델로 예측, OpenCV 실습 |
| `image/001~003.jpg`, `AS.jpg`, `KIA.jpg`, `NA.gif` | 이미지 처리 실습 |
| `image/*.mp4` (matrix, korea 등) | 영상 처리, 객체 탐지 실습 |

### 10. 파이썬 기초 (`scripts/`)
| 파일 | 내용 |
|---|---|
| `myModule.py` | 사용자 정의 함수 (`hi`, `addition`, `subtraction` lambda, `add_all(*inputs)`) |
| `myLibrary.py` | 클래스, 다중 상속 예제 (`Calculator`, `Calculator_2`, `myComputer`) |
| `__init__.py` | 패키지 import 실습 |

```python
from scripts.myModule import add_all
from scripts.myLibrary import myComputer
```

---

## 📦 분할 압축 파일 합치기

GitHub의 파일당 100MB 제한 때문에 큰 데이터는 나눠서 올렸습니다. **같은 이름의 조각을 모두 받은 뒤** 합쳐서 푸세요.

**분할 zip** (`animals_part.z01, .z02, .zip` / `maskdataset_3C_Part.z01~.z04, .zip`)
```bash
# Linux / Colab
zip -s 0 animals_part.zip --out animals.zip
unzip animals.zip
```
Windows에서는 7-Zip이나 반디집으로 `.zip` 파일을 열면 자동으로 합쳐집니다.

**분할 tar** (`maskdataset_3C.taraa ~ .tarae`)
```bash
# Linux / Colab
cat maskdataset_3C.tara* > maskdataset_3C.tar
tar -xf maskdataset_3C.tar
```
```bat
:: Windows (cmd)
copy /b maskdataset_3C.taraa+maskdataset_3C.tarab+maskdataset_3C.tarac+maskdataset_3C.tarad+maskdataset_3C.tarae maskdataset_3C.tar
```

---

## ⚠️ 참고
- 한글 CSV 중 일부는 UTF-8(BOM) 인코딩입니다. 글자가 깨지면 `encoding="utf-8-sig"` 또는 `encoding="cp949"`를 지정하세요.
- 공개 데이터셋(Kaggle, UCI, MovieLens, NSMC, IMDB, GloVe 등)의 저작권과 라이선스는 각 원 출처를 따릅니다. 교육용으로만 사용하세요.
