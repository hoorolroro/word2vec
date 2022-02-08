# word2vec
## word2vec이란?
● 단어를 0이나 1로 표현하는 one-hot encoding은 유사한 단어끼리의 유사도 표현이 불가능하다.  
cos_sim(apple, fruit) = 0  
cos_sim(apple, car) = 0  

● 단어를 실수로 표현하는 Distributed Representation  

<img src="https://user-images.githubusercontent.com/98728682/152904099-a67b7e89-c412-483e-8176-eb626858d3d2.png" width="520" height="400">  

● 단어를 0 혹은 1이 아닌 연속적인 레벨로 표현을 하는 기법이다.  
● word2vec은 특정 단어의 의미를 벡터로 표현하기 위해서는 주변 문맥을 이용한다는 Distributional hypothesis[Harris et al., 1954] 철학을 이용  
● word2vec은 Tomas Mikolov에 의해서 2013에 제안되었다.  
## Project 목표  
● Pre-trained word2vec(GoogleNews-vectors-negative3000.bin.gz)를 사용해서 단어의 Similarity와 Word Analogy를 파악해본다.
● Word2vec을  Custom data를 바탕으로 새로 학습해본다. 
● word2vec을 하이퍼파라미터를 바꿔가면서도 새로 학습해본다.
