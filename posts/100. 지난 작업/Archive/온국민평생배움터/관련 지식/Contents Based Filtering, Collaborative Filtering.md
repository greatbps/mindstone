#### 콘텐츠 기반 필터링(content based filtering)

콘텐츠 기반 필터링 방식은 사용자가 특정 아이템을 선호하는 경우 그 아이템과 비슷한 콘텐츠를 가진 다른 아이템을 추천해주는 방식입니다.

![](https://blog.kakaocdn.net/dn/bv2zdZ/btqAQlChGVr/Obnr5AeadnE15JAlOj3yQ1/img.jpg)

굉장히 단순한 아이디어입니다.

예를 들어 사용자 A가 ItemA에 굉장히 높은 평점을 주었는데 그 Item이 액션 영화이며 '이수진' 이라는 감독이었으면 

'이수진'감독의 다른 액션 영화를 추천해주는 것입니다.

그렇기 때문에 잘 사용하지 않는 방법입니다. 예전에는 많이 사용했던 방법이라고 합니다.

#### 협업 필터링 - nearest neighbor based collaborative filtering

협업 필터링(collaborative filtering)에는 위에서도 말씀드렸지만 최근접 이웃 기반(nearest neighbor based collaborative filtering)과 잠재 요인(latent factor based collaborative filtering) 협업 필터링이 있다고 말씀드렸습니다.

이번 포스팅에서는 최근접 이웃 기반 nearest neighbor collaborative filtering에 대해서 알아보고 다음 포스팅에서 잠재 요인 collaborative filtering에 대해서 포스팅을 하겠습니다.

우리가 살아가는 실 생황에서 새로운 영화(예를 들어 최근에 나온 포드 v 페라리)가 나오면 다른 사람들의 평점이나 평가를 들어본 뒤 영화를 선택하는 경우가 대부분입니다. (그냥 봤다가 재미없으면 시간 낭비, 돈 낭비이기 때문이죠)

이 처럼 사용자가 아이템에 매긴 평점, 상품 구매 이력 등의 사용자 **행동 양식(user behavior)를 기반으로 추천 해주는 것이 collaborative filtering 입니다.**

그 중 최근접 이웃 기반(nearest neighbor collaborative filtering)은 사용자-아이템 행렬에서 사용자가 아직 평가하지 않은 아이템을 예측하는 것이 목표입니다.

![](https://blog.kakaocdn.net/dn/bewru7/btqAPdR0ZmZ/4mkjMs32LYMoI7fnfAve3k/img.jpg)

위 그림처럼 예를들어 User2가 아직 ItemC에 대해 평가를 내리지 않았으니 이를 어떻게 평가할 지 예측하는 것입니다.

이처럼 nearest neighbor 기반 협업 필터링에서는 사용자-아이템 평점 행렬과 같은 모습을 가지고 있어야합니다. 따라서 column은 Item이 되어야하고 row는 user가 되어야 하는 듯한 모습을 가지고 있어야합니다.

![](https://blog.kakaocdn.net/dn/p45kL/btqARXfVVI5/6oHnJ5yksLHBhlt3KMqPek/img.jpg)

그렇기 때문에 위 그림의 왼쪽 사진과 같이 데이터가 주어지면 오른쪽과 같이 데이터를 변경해주어야 합니다.

이러한 변경 방법은 Python pandas에서 pivot table로 지원해줍니다.

그리고 저런 모습은 공간 낭비가 됩니다. 왜냐하면 데이터가 굉장히 Sparse하기 때문이죠. 지금이야 Item이 몇 개 없지만 유튜브나 넷플릭스 같은 서비스에서는 Item이 수만개 ~ 수억개가 될 것입니다. 사용자가 이러한 동영상을 다 봤을리가 없죠. 

이러한 최근접 이웃 기반(nearest neighbor based collaborative filtering)은 또 2가지로 나뉘어집니다.

-   사용자 기반 : 비슷한 고객들이 ~한 Item을 소비했다
-   아이템 기반 : ~한 Item을 소비한 고객들은 다음과 같은 상품도 구매했다

사용자 기반의 협업 필터링(user based collaborative filtering)은 아래와 같은 모습을 가지고 있을겁니다.

![](https://blog.kakaocdn.net/dn/tSWlg/btqARjDOb6e/H3eUhClUaVvNrLjIlkrIBK/img.jpg)

즉, User1과 User2는 ItemA ~ C까지의 평점이 비슷하기 떄문에 비슷하다~ 라고 생각하는 것이죠.

아이템 기반 협업 펄터링(Item based collaborative filtering)은 아래와 같습니다.

![](https://blog.kakaocdn.net/dn/MN4no/btqAN4O2SsW/YfwwaaaGoTqwNARWE73k40/img.jpg)

아까와 다르게 item - user 행렬을 가지고 있습니다.

ItemA와 ItemB는 비슷한 평점 분포를 가지고 있습니다. 그래서 ItemA와 ItemB는 서로 유사하다고 하는 것입니다.

그래서 User4에게 ItemA을 추천해주는 것이죠!

일반적으로 사용자 기반 협업 필터링(user based collaborative filtering)보다 아이템 기반 협업 필터링(item based collaborative filtering)이 좀 더 정확도가 높다고 합니다.

그 이유는 대체적으로 생각하는 것이 비슷한 상품을 좋아한다고 취향이 비슷하지 아니니까~ 라고 많이들 말씀하십니다.

그래서 nearest neighbor collaborative filtering을 사용할 때는 아이템 기반 협업 필터링을 많이 사용한다고 합니다.
