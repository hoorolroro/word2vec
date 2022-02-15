# word2vec
## word2vec이란?
● 단어를 0이나 1로 표현하는 one-hot encoding은 유사한 단어끼리의 유사도 표현이 불가능하다.  

cos_sim(apple, fruit) = 0  
cos_sim(apple, car) = 0  

● 아래는 단어를 실수로 표현하는 Distributed Representation을 묘사하는 그림이다.  

<img src="https://user-images.githubusercontent.com/98728682/152904099-a67b7e89-c412-483e-8176-eb626858d3d2.png" width="450" height="350">  

● Distributed Representation은 단어를 0 혹은 1이 아닌 연속적인 레벨로 표현을 하는 기법이다.  

● word2vec은 특정 단어의 의미를 벡터로 표현하기 위해서는 주변 문맥을 이용한다는 Distributional hypothesis[Harris et al., 1954] 철학을 이용  

● Tomas Mikolov에 의해서 2013에 제안되었다. [Mikolov et al. 2013]  
## Project 목표  
● Pre-trained word2vec(GoogleNews-vectors-negative3000.bin.gz)를 사용해서 단어의 Similarity와 Word Analogy를 파악해본다.  

● Word2vec을  Custom data를 바탕으로 새로 학습해본다.  

● 두 번 째 실습에서는 word2vec를 하이퍼파라미터를 바꿔가면서도 새로 학습해본다.  

## Hyper-parameter  

|size|window|min_count|workers|sg|hs|negative|ns_exponent|alpha|min_alpha|iter|accuracy| 
|---|---|---|---|---|---|---|---|---|---|---|---|  
|300|10|5|4|0|0|15|0.75|0.01|0.0001|3|25.9%|  
|300|10|5|4|0|0|17|0.75|0.01|0.0001|3|26.0%|
|300|10|5|4|1|0|17|0.75|0.01|0.0001|3|39.0%|
|300|10|5|4|0|0|20|0.75|0.01|0.0001|3|26.8%|
|300|10|5|4|1|0|20|0.75|0.01|0.0001|5|45.2%|
|300|10|5|4|1|0|15|0.75|0.01|0.0001|5|45.4%|


## 프로그램 시현
● Skip gram을 사용하지 않았을 경우, Negative sampling 수를 15에서 20까지 점진적으로 늘릴수록 정확도가 높아졌다.

● Skip gram을 사용하였을 경우에서 Negative sampling 수를 15에서 20까지 변화하였을 경우 정확도의 변화량을 확인하지 못하였다.

● 전반적으로 Skip gram을 사용하고, iter를 늘리면 정확도가 확연히 높아진 것을 확인하였다.(최종적으로 45.4%를 얻었다.)
