# kaggle_tweeter
Kaggle Tweeter code repository
-------

# 회의 및 아이디어 기록 (Posts on ideas and meetup)
- [23 April] EDA 및 모델링 아이디어 공유

1. 전처리도 거의 필요가 없는 대회. 따라서 **Bert모델 기반으로 어떻게 점수 올릴지 고민하는 것이 관건**이다.

1-1. tokenization (wordpiece vs nltk tokenization vs ...): 하지만 bert-pretrain은 wordpiece tokenizing이라 pretrained model을 사용할 수 없다.

1-2. BERT + NAS ?: 현재 SOTA가 NAS추가한 것. 하지만 NAS는 따로 공부가 필요함.

1-3. pretrain (from the bottom) with social data.

1-4. Post-processing: ex) `neutral`이면 `text`그대로 사용.

1-5. **Bert에 input data를 다양한 방식으로 넣어보기.** 

2. 다양한 접근법. 

2-1. NER로 풀기 (Spacy 모듈 이용)

2-2. 단어마다 gini impurity를 구해 단어의 weight를 주기.

2-3. uni-gram & bi-gram으로 피처 만들어 xgboost 돌리기. 

3. 새로 배운 사실. 

3-1. torch에서 out이 의미하는 바가 . 따라서 out[-1]는 last layer(encoder) output이고 out[-2]는 second to last layer output이다. 커널에서는 주로 output[-1] + output[-2] 두 layer를 concat해서 사용한다.

3-2. ensemble은 5 fold를 의미한다. 
