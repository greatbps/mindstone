### 액티브 러닝이란?

전통적으로 기계학습(Passive Machine Learning)은 라벨링되지 않은 데이터에 대해 사람이 라벨을 부여하면 이를 기계가 학습하는 방식으로 이루어졌다. 이 방식에서는 학습 데이터 마련에 상당한 사람의 공수가 들어간다. 뿐만아니라 이미지넷 리더보드나 기계번역 모델을 보면 사람보다도 태스크를 잘 수행하는 모델이 등장하였는데, 이렇게 잠재적으로 뛰어난 기계를 두고 사람이 모든 라벨링을 진행하는 것은 조금 아깝다는 생각이 든다. 어떤 데이터가 필요한지를 기계가 판단하여 사람에게 라벨링을 부탁하면 사람은 더 적은 라벨링 공수를 들이고도 좋은 모델을 학습할 수 있지 않을까?

이것이 액티브러닝의 아이디어다. ==액티브러닝에서는 기계가 라벨링이 필요한 데이터 중 자동적으로, 그리고 점진적으로 가장 정보량이 많은 데이터를 선택하는 것을 목표로 한다. ==초기 라벨링된 일부 데이터를 이용해 모델은 학습을 시작하고, 아직 라벨링이 이루어지지 않은 데이터 중 학습에 중요한 것들에 대해 라벨링을 요구한다. 이후 정보량이 풍부한 데이터를 이용해 학습 진행 및 데이터를 요구하는 사이클을 통해 모델은 점차 고도화된다. 

![](https://blog.kakaocdn.net/dn/sFd96/btqGirv3Vhs/giI8h6RdiD8lfqwvIeJ0s1/img.png)![](https://blog.kakaocdn.net/dn/Y3XYy/btqGishAHQX/OaVY0ywxxsd3yPwckOB81k/img.png)

&lt;Source: ICML 2019 active learning tutorial&gt;

---

### 액티브 러닝 시나리오

학습 모델(러너, learner)가 데이터 인스턴스에 대한 라벨을 쿼리도록 하기 위해 다음과 같은 세 가지 셋팅을 자주 사용한다.

#1. Membership Query Synthesis

러너가 주어진 분포에 의거하여 데이터 인스턴스를 생성 혹은 구성하여 쿼리하는 것을 의미한다. 예를 들어, 숫자 이미지 분류 문제를 풀고자 할 때 학습모델은 숫자 이미지와 비슷한 이미지(약간 회전되거나 크롭되는 등..)를 만들어내고, 이를 라벨러에게 전송하여 라벨링을 요구한다.

![](https://blog.kakaocdn.net/dn/wDUQn/btqGewyBhJH/ddZ2JWK7n3mNPsK4N7Nr20/img.png)

<Source: datacamp active learning tutorial>

#2. Stream-Based Selective Sampling

라벨링되지 않은 데이터는 아주 쉽게 얻을 수 있는 경우 사용하는 전략이다. 러너는 라벨링되지 않은 인스턴스를 보고, 해당 인스턴스가 가진 정보량에 의거해 이것이 라벨링될 가치가 있는지 아닌지를 결정한다. 이때 인스턴스가 가진 정보량을 평가하기 위해 query strategy라는 것을 사용한다. 모델이 라벨링이 필요하다고 판단한 이미지는 쿼리하고, 아닌 것은 버리는 과정을 반복하며 학습이 이루어진다.

![](https://blog.kakaocdn.net/dn/uZHQk/btqGh5trbmp/ShGf5Y6wvONJzRlFBsDC6K/img.png)

<Source: datacamp active learning tutorial>

#3. Pool-Based Sampling(*)

이 방식은 가장 널리 사용되는 방법으로, 라벨링되지 않은 큰 데이터 풀이 존재할 때 사용하는 전략이다. 여기서는 데이터풀에서 정보량 측도에 의거해 인스턴스들을 가지고오게 된다. 이때 정보량 측도는 데이터풀에 있는 모든 인스턴스들에 대해 적용을 하고, 그중 가장 정보량이 많은 것들을 선택하는 식이다. 

![](https://blog.kakaocdn.net/dn/bYge1J/btqGishA6lv/UlUodeq23UIJYd1WNNnqWK/img.png)

<Source: datacamp active learning tutorial>

---

### 라벨이 필요한 인스턴스를 선택하는 전략 (Query Strategy)

액티브러닝의 핵심은 과거에 모델이 쿼리했던 인스턴스와 그에 대한 답변(라벨)에 의거하여 러너가 필요한 인스턴스를 쿼리하는 능력에 있다. Uncertainty Sampling 이라는 개념에서 query strategy 세 가지를 예시로 살펴보자.

다음 표는 두 개의 데이터 포인트와, 각 데이터포인트가 세 개의 라벨에 속할 확률을 각각 나타낸다.

데이터포인트

라벨 A

라벨 B

라벨 C

d1

0.9

0.09

0.01

d2

0.2

0.5

0.3

**Least Confidence(LC)**

- 이 전략에서 학습자는 가장 "확실하게" 예측한 라벨에 대해 가장 확신도가 낮은 예제를 선택한다.

- d1은 라벨 A을 0.9의 확신도로, d2는 라벨 B를 0.5의 확신도로 가지고 있다. 따라서 러너는 d2의 실제 라벨을 알고싶어한다.

- 이 방법은 가장 그럴듯한 라벨에 대한 확신도만을 사용하고, 다른 라벨에 대한 확률은 고려하지 않는다.

**Margin Sampling** 

- LC에서 최고 확률의 라벨 이외의 것을 고려하지 않는다는 점을 보완하기 위해 고안된 방법.

- 가장 확률이 높은 라벨과 두 번째 라벨의 확신도의 차이가 적은 예제를 선택하는 전략이다.

- d1은 0.9 - 0.09 = 0.81, d2는 0.5 - 0.3 = 0.2의 점수를 받고, 러너는 역시 d2에 대한 Ground Truth 라벨을 요구한다. 

**Entropy Sampling**

- 이 방법은 모든 가용한 라벨 확률값을 모두 사용하는 방법으로, entropy 개념을 사용한다.

- 엔트로피를 구하는 식을 각각의 예제에 적용하고, 엔트로피(=불확실성)가 가장 큰 예제를 쿼리하는 방식이다.ㅣ

- d1의 엔트로피는 0.115, d2의 엔트로피는 0.447로, 역시 d2를 쿼리하게 된다.

![](https://blog.kakaocdn.net/dn/HM2r8/btqGDQjTFWG/WyMIuvj5drhjogtFeNKH0K/img.png)

<Source: Wikipedia>

---

### 액티브 러닝, 스탭 바이 스탭

Step 0. 데이터 수집

- 실제 데이터의 분포를 반영하도록 데이터셋을 수집한다.

- 이때 수집되는 데이터는 라벨링되지 않은 데이터셋. 

Step 1. 데이터셋 분할

- 모델 학습에 사용할 시드 데이터(Seed, labelled)와 이외의 라벨링되지 않은 데이터를 나눈다.

- 수집한 데이터 중 일부는 라벨링이 이루어지고, 나머지 부분은 라벨링되지 않은 상태로 남아있다.

Step 2. 모델 학습

- 일반적인 기계학습과 같은 방법(cross-validation 등)으로 라벨링된 데이터를 학습한다. 

- 이 과정을 통해 러너는 데이터 도메인에 대한 지식을 학습하게 된다.

Step 3. 라벨링되지 않은 데이터 중 선택

- query strategy를 이용해 추가적으로 라벨링이 필요한 데이터를 선택한다. 

Step 4. 학습 중단 기준 마련

- 이제 어떤 기준에 만족할 때까지 Step 2~3을 반복하며 모델을 고도화하게 된다.

- 예를 들어, test 데이터를 미리 나누어 두고, 이 테스트 데이터에 대한 성능이 나아지지 않으면 과정을 중단하게 한다.

---

** 참고자료 **

- ICML 2019 tutorial ([Link](https://icml.cc/Conferences/2019/ScheduleMultitrack?event=4341))

- CS CMU slide ([Link](https://www.cs.cmu.edu/~tom/10701_sp11/recitations/Recitation_13.pdf))

- Datacamp active learning tutorial ([Link](https://www.datacamp.com/community/tutorials/active-learning))