# Word2Vec을 이용한 가사 기반 노래 추천시스템

### 1. 멜론 데이터 크롤링
멜론에서 발라드 장르의 1위부터 50위까지의 곡의 가사를 크롤링한다.

### 2. 데이터 확인
수집된 데이터를 데이터프레임 형식으로 저장하고, 각 컬럼에는 노래의 제목, 가수, 앨범 커버 그리고 가사 데이터가 포함되어 있다.

![image](https://user-images.githubusercontent.com/63490319/209513441-5bfb1fa8-4fa0-4e15-9839-a675207f3469.png)


### 3. 데이터 전처리
가사 데이터를 Word2Vec 모델에 학습시키기 위해 토큰화하는 과정을 거친다.
이 때, 먼저 띄어쓰기와 한글 외 문자를 제거하고, 불용어를 처리한다.

![image](https://user-images.githubusercontent.com/63490319/209513507-5c44006c-ed8d-48bb-b6cd-6e5633fdc7e2.png)

### 4. EDA, WordCloud
Word2Vec 모델의 파라미터를 결정하기 위해 노래 당 토큰 개수를 확인하고, wordcloud를 통해 많이 나온 단어들을 확인한다.

![image](https://user-images.githubusercontent.com/63490319/209513591-e09ace52-56e9-4385-ac18-1201b9948b7d.png)

![image](https://user-images.githubusercontent.com/63490319/209513689-7184c096-ee72-447c-9a86-26f37231ee91.png)

### 5. Word2Vec
사전 학습된 Word2Vec을 사용해 단어를 임베딩해 단어 벡터 매트릭스를 만든다.

![image](https://user-images.githubusercontent.com/63490319/209514295-db5a93cd-450d-4313-8fb3-caab11478545.png)

### 6. 단어 벡터의 평균 구하기
각 노래에 대해 모든 단어들의 벡터값 평균을 구해 가사 벡터 리스트를 만든다.

### 7. 코사인 유사도 구하기
50곡의 가사 벡터 리스트를 통해 코사인 유사도를 구한다.

![image](https://user-images.githubusercontent.com/63490319/209514372-5e023648-0357-4bc8-a639-00431bf9622e.png)

### 8. 추천시스템 구현
특정 노래 제목을 입력하면 해당 노래와 가장 유사한 5곡이 추천된다.

![image](https://user-images.githubusercontent.com/63490319/209514200-7d46a740-0edf-43b3-ae5b-9a5c3ff6124d.png)
