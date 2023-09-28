**QuantConnect는 전략을 개발, 테스트 및 실행할 수 있는 알고리즘 거래 브라우저 기반 플랫폼입니다.


![[Pasted image 20230928141009.png]]

링크: [https ://www.퀀트커넥트.com](https://www.quantconnect.com/)

그들은 테라바이트 규모의 무료 금융 데이터를 제공하고 자체 데이터나 주요 중개업체 컬렉션의 데이터를 사용하여 실시간 거래(서류 거래 포함)와 전략 백테스트를 모두 허용합니다. 주식, 선물, 옵션, 외환, CFD 및 암호 화폐를 지원합니다.

이 플랫폼은 아무것도 없는 상태에서 인프라에서 실시간으로 실행되는 완전히 검증되고 백테스트된 전략을 갖출 수 있도록 정말 쉬운 올인원 위치로 설계되었습니다.

기본 기능 외에도 QuantConnect에는 **전략 개발 프레임워크** (다양한 조합으로 활용될 수 있는 알고리즘 전략의 주요 측면을 다루는 일련의 사전 제작된 플러그 앤 플레이 모듈)와 같은 정말 훌륭한 측면이 있습니다. 그리고 Alpha Stream은 귀하의 알고리즘에 의해 생성된 통찰력과 거래 권장 사항을 확인하고 실제로 사용하지 않고도 활용할 수 있는 관심 있는 제3자에게 전략을 "임대"하여 귀하가 보유할 수 있는 전략으로 수익을 창출할 수 있는 기능입니다. 기본 코드를 보는 것입니다.

## 왜 QuantConnect를 사용해야 합니까?

- 백테스팅 및 실시간 거래
- 종이 거래
- 무료 데이터
- 전략 개발 프레임워크
- 알파 스트림
- 포럼

#### 백테스팅 및 실시간 거래

대부분의 플랫폼과 API를 통해 실시간 거래 전략을 쉽게 실행할 수 있지만, QuantConnect의 독특한 측면은 플랫폼을 사용하여 전략에 철저한 백테스트를 제공하는 것이 얼마나 쉬운지입니다.

당신이 해야 할 일은 백테스트 기간의 시작 날짜와 종료 날짜, 전략에 할당할 초기 현금 금액을 구성하고 "백테스트"를 누르는 것뿐입니다. 그러면 끝입니다!

![[Pasted image 20230928141806.png]]

그러면 매우 포괄적인 백테스트 통계와 그래프가 제공됩니다!

![[Pasted image 20230928141845.png]]

백테스팅은 무료이지만 라이브 트레이딩을 위해서는 알고리즘을 강화하기 위해 월간 Quant Researcher 멤버십(월 8달러)과 라이브 트레이딩 노드(최소의 경우 월 20달러)에 대한 소액 투자가 필요합니다.

[여기서는](https://algotrading101.com/learn/quantconnect-guide/#Back-testing-vs-Live-trading) 이에 대해 더 자세히 살펴보겠습니다 !


## 종이 거래

살기 위한 전략을 전개할 때 실제 돈을 사용하기 전에 전략을 테스트하기 위해 "서류 거래"(가짜 돈을 사용하여 거래)를 선택할 수 있습니다.

이것은 일반적인 거래의 초보자인 경우와 모든 거래자(초보자와 경험자 모두)에게 거래 전략을 실행하기 전에 실제로 샘플 외 데이터에서 수익성이 있다는 더 나은 느낌을 얻는 데 매우 유용합니다.

_종이 거래는 Go Live_ 흐름 의 "중개 선택"(“Select Brokerage”) 단계에서 선택할 수 있습니다 .
![[Pasted image 20230928142212.png]]

#### 무료 데이터

[QuantConnect는 QuantConnect Data Explorer를](https://www.quantconnect.com/data/tree) 통해 엄청난 양의 무료 데이터를 제공합니다 .

![[Pasted image 20230928142244.png]]
IDE 내에서는 모두 무료로 사용할 수 있지만 외부 환경에서 다운로드하여 사용하는 것이 반드시 무료인 것은 아닙니다. 때로는 비용을 지불해야 할 수도 있습니다.

나중에 데이터 탐색을 위해 알고리즘/QuantConnect의 Jupyter 노트북 내에서 이 데이터를 사용하는 방법을 보여드리겠습니다.

#### 알파스트림

QuantConnect의 [Alpha Stream은](https://www.quantconnect.com/market) [](https://www.quantconnect.com/terminal/#market)퀀트가 공개 시장에서 개발한 모든 알파를 임대할 수 있는 정말 멋진 기능입니다.

알파는 자산의 가격 상승 또는 하락이 예상되는지, 때로는 예상되는 변화의 규모와 지속 기간을 자세히 설명하는 통찰력, 즉 예측을 _생성 하는 알고리즘입니다._

그런 다음 펀드는 이를 사용하여 포트폴리오를 관리할 수 있습니다. Alphas는 이러한 예측에만 초점을 맞추고 포지션 크기 조정, 포트폴리오 관리 및 위험을 적극적으로 무시합니다.

모든 이해 당사자/펀드는 "공유 가격"(다른 사람도 동일한 알파를 사용할 수 있음) 또는 다른 사람이 동일한 알파를 사용하지 못하도록 차단하는 "독점 가격"으로 알파 사용을 임대할 수 있습니다.

그런 다음 알파를 사용하여 자신의 자금을 거래하거나 샘플 외부 데이터에서 테스트할 수 있지만 소스 코드를 볼 수는 없습니다. QuantConnect는 Alpha의 리버스 엔지니어링을 최대한 어렵게 만들기 위해 특별한 주의를 기울입니다.

마켓플레이스는 전략을 비교하여 구매가 정보에 입각한 결정을 내리는 데 도움이 되는 다양한 주요 통계를 보여줍니다.

![[Pasted image 20230928142422.png]]


[여기에서](https://www.quantconnect.com/docs/algorithm-framework/alpha-creation) 알파 생성에 대한 자세한 내용을 읽을 수 있지만 나중에 가이드의 [QuantConnect 알파 생성 예제 사용: 스마트 인사이더](https://algotrading101.com/learn/quantconnect-guide/#Using-QuantConnects-Alpha-Creation-example-Smart-Insider) / [인사이트 생성](https://algotrading101.com/learn/quantconnect-guide/#Generating-Insights) 섹션 에서 알파 생성 방법을 보여드리겠습니다 .

#### 전략 개발 프레임워크

QuantConnect의 [전략 개발 프레임워크](https://www.quantconnect.com/docs/algorithm-framework/overview) (SDF)는 전략의 특정 구성 요소를 최대한 쉽게 복제, 공유 및 재사용할 수 있도록 설계된 플러그 앤 플레이 모듈로 구성됩니다.

그것은 5개의 섹션으로 구성되어 있습니다.

- Alpha **Creation** 섹션(방금 논의한 바와 같이 자산의 가격 상승 또는 하락이 예상되는지 여부와 예측의 규모, 기간 및 신뢰도를 나타내는 시장에 대한 통찰력을 생성하는 알고리즘).
- 유니버스 선택(유동성, 변동성, 시가총액 등과 같은 모든 종류의 지표로 필터링 가능한 전략으로 거래할 자산을 선택하는 모듈)
- 포트폴리오 구성(유니버스의 다양한 자산에 할당된 자금 균형을 결정하는 모듈)
- 실행(귀하의 알고리즘이 포트폴리오 구성 섹션에서 결정한 목표 할당에 도달하는 방법을 결정하는 모듈. 예를 들어 즉시 실행 또는 표준 편차 - 알고리즘은 거래를 실행하기 전에 가격이 최근 평균보다 X 표준 편차 위 또는 아래로 움직일 때까지 기다립니다) .
- 위험 관리(위험 최소화 및 손실 포지션 조기 축소에 초점을 맞춘 모듈)

눈치채셨겠지만, 모듈 사이에는 명확한 방향 흐름이 있습니다.

![[Pasted image 20230928142648.png]]

[처음에는 이 모든 것이 다소 부담스러워 보일 수 있지만 걱정하지 마십시오. QuantConnect의 전략 개발 프레임워크란 무엇입니까?](https://algotrading101.com/learn/quantconnect-guide/#What-is-QuantConnects-strategy-development-framework) 의 예제를 통해 모든 것을 심층적으로 다룰 것입니다. 가이드 부분!

#### 포럼

마지막으로 QuantConnect에는 자체 [포럼이](https://www.quantconnect.com/forum/discussions/1/interesting) 있습니다 .

동료 트레이더들과 전략 및 테스트를 토론하고 공유할 수 있으며, 알려진 다양한 데이터 문제에 대한 도움을 받을 수 있고, 진행 중인 다양한 대회를 확인하거나 참가할 수 있습니다.


## 왜 QuantConnect를 사용하면 안 되나요?

- 학습 곡선
- 완전 무료는 아님
- 귀하의 작업은 서버에 저장됩니다

전체적으로 QuantConnect는 매우 유용한 플랫폼입니다.

**학습 곡선**

이 기능을 사용하지 않는 가장 큰 이유는 모든 기능을 이해하기가 너무 부담스럽기 때문일 수 있습니다. 하지만 이것이 바로 이 가이드의 목적입니다!

즉, 확실히 학습 곡선이 있지만 플랫폼을 둘러보는 방법을 알고 나면 많은 일이 얼마나 쉽게 만들어졌는지 깨닫게 될 것입니다.

그러나 바로 알고리즘 테스트를 진행하고 싶다면 이미 익숙한 더 간단한 설정을 사용하는 것이 더 나을 수도 있습니다.

**완전 무료는 아님**

또한, QuantConnect의 모든 구성요소가 완전히 무료인 것은 아닙니다. 우리는 무엇이 무엇인지, 아닌지를 잠시 후에 정확히 다룰 것입니다!

**귀하의 작업은 서버에 저장됩니다**

귀하의 코드는 로컬 컴퓨터가 아닌 QuantConnect 서버에 저장됩니다.

따라서 보안 위험과 허가 없이 코드에 액세스하는 것을 조심할 수 있습니다.

즉, QuantConnect는 보안을 중요하게 생각하는 것 같습니다. [여기에서](https://www.quantconnect.com/blog/values-security-and-user-intellectual-property/) 그들의 진술을 참조하십시오 .

[관련 메모에서 QuantConnect를 사용하면 완전한 오픈 소스 알고리즘 거래 엔진 인 LEAN을](https://github.com/QuantConnect/Lean) 자체 호스팅할 수 있습니다 .

## QuantConnect는 무료인가요?

QuantConnect가 제공하는 가장 낮은 계층의 노드를 사용한 백테스트는 완전 무료입니다.

QuantConnect에서 실시간 거래를 할 수 있는 최소 투자액은 Quant Researcher 멤버십의 경우 월 $8이고 L-Micro 라이브 노드(1 CPU/0.5GB RAM)의 경우 추가로 $20/월입니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/09/paid-tier-selection.png)

백테스팅 노드와 라이브 거래 노드를 추가로 업그레이드하고 백테스팅 속도를 높이거나 병렬 백테스팅을 허용하기 위해 추가 비용으로 다양한 계층의 연구 노드를 구매할 수도 있습니다.

![[Pasted image 20230928143200.png]]

매달 4개의 사용 가능한 티켓으로 이메일 지원에 액세스할 수 있는 QuantConnect의 "브론즈 계층"을 잠금 해제하므로 다양한 구성 요소에 월 40달러 이상을 지출할 가치가 있습니다.

계획을 보려면 [여기로](https://www.quantconnect.com/pricing?organization=134bbb09b1653b775995c5c78a6f463a) 이동하세요 .

QuantConnect는 또한 IDE 내에서 무료로 사용할 수 있는 방대한 양의 과거 데이터를 제공하지만 QuantConnect 외부에서 다운로드하려면 데이터 세트별로 비용을 지불해야 할 수도 있습니다.

학생이라면 QuantConnect에서 연구원 등급에 대한 1년 무료 액세스를 매우 친절하게 제공합니다!

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/09/free-year-for-students.png)

## QuantConnect는 Python을 지원합니까?

예, QuantConnect는 IDE 내에서 Python과 C#을 모두 지원합니다. 하지만 두 언어는 전략 개발 프레임워크에서 사용 가능한 모듈 세트가 약간 다릅니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/09/languages.png)

## QuantConnect를 어떻게 시작하나요?

#### 가입 및 회원가입

[먼저 가입](https://www.quantconnect.com/signup) 페이지 로 이동하여 계정을 만드세요.

백테스트만 하고 싶다면 더 이상 아무것도 할 필요가 없습니다. [연구실/터미널](https://www.quantconnect.com/terminal/#my-projects) 로 가서 알고리즘 구축을 시작해 보세요!

실시간 거래를 원할 경우 [계정 업그레이드](https://www.quantconnect.com/pricing?organization=134bbb09b1653b775995c5c78a6f463a) 페이지로 이동하여 Quant Researcher 멤버십과 실시간 거래 노드를 구매하세요. 하지만 원하는 경우 몇 가지 전략을 백테스트한 후까지 기다릴 수 있습니다.

#### 문서

우리는 이 가이드에서 QuantConnect의 주요 기능 중 일부에 대한 단기 집중 코스를 제공할 것입니다. 그러나 추가 도움이 필요하거나 일반적으로 더 자세히 배우고 싶은 경우를 위해 QuantConnect는 매우 철저한 문서를 제공 [합니다](https://www.quantconnect.com/docs) .

#### 부트캠프

QuantConnect의 연구실/터미널 섹션에서 찾을 수 있는 [Bootcamp](https://www.quantconnect.com/terminal/#bootcamp) 도 마찬가지로 유용합니다 .

여기에서는 힌트와 전체 솔루션이 제공되는 QuantConnect의 기본 기능을 다루는 일부 코드/알고리즘을 단계별로 안내합니다.

이 강의는 무언가를 구현하는 방법을 정확히 잊어버렸거나 특정 사용 사례에 맞게 템플릿을 약간 조정하려는 경우 참조하는 데 매우 유용할 수 있습니다.


## QuantConnect에서 백테스트 전략을 수행하는 2가지 방법 – Classic vs SDF

**방법 1(클래식 방법):** 기본 알고리즘을 처음부터 코딩합니다. 구매 및 판매 논리를 설정하고 이를 기반으로 거래를 시작합니다.

**방법 2(전략 개발 프레임워크 AKA SDF):** 앞서 언급했듯이 SDF에는 많은 수정 없이 구현할 수 있는 즉시 사용 가능한 모듈이 있습니다. 이 모듈은 5단계를 다룹니다.

1. **유니버스 선택**  (거래할 자산 선택)
2. **Alpha Creation**  (거래 신호 생성)
3. **포트폴리오 구성**  (보유 자산별 목표 설정)
4. **실행**  (목표 달성을 위한 실행 방법)
5. **위험 관리**  (성과가 좋지 않을 때 포트폴리오 요소를 청산하는 논리 설정)

SDF에 대해서는 이후 섹션에서 자세히 다루겠습니다.

## 연구실/터미널 및 첫 번째 알고리즘 생성

#### 첫 번째 알고리즘 만들기

랩/터미널은 모든 알고리즘을 작성하는 곳입니다.

예전에는 QuantConnect의 "클래식"(자신만의 코드 없음 SDF 모듈)과 "프레임워크"/SDF 알고리즘 사이에 뚜렷한 구분이 있었지만 요즘에는 구분이 더 유동적입니다.

시작하려면 왼쪽 패널에서 "새 알고리즘 만들기"를 클릭하세요.

아래 이미지의 오른쪽에서 볼 수 있듯이 **main.py** 에는 모든 코드가 들어갑니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/framework-vs-classic-2048x979.png)

자신만의 고전적인 알고리즘을 처음부터 작성하고 싶다면 여기에서 코딩을 하게 됩니다.

전략 개발 프레임워크 모듈 중 일부를 사용하려는 경우 해당 모듈은 오른쪽 코드에 미리 만들어진 개체로 삽입됩니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/adding-smart-insider-module.png)

Smart Insider 모듈 추가

기본 프로세스는 사용하려는 SDF 모듈을 선택한 다음(원하는 경우 일부/전체를 건너뛰고) 오른쪽 하단의 “알고리즘 생성”을 누르는 것입니다.

원하는 만큼 알파 모듈을 추가할 수 있지만 프레임워크의 다른 섹션에 대해서는 단일 모듈만 선택할 수 있습니다.

_Create Algorithm을_ 누르면 **main.py** 내에서 수동으로 코드를 작성할 수 있습니다 .

#### 기본 구조

일부 SDF 모듈을 사용하여 알고리즘을 생성하는 경우 다음과 같은 **main.py가** 남아 있어야 합니다 .

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/algo-creation-example.png)

SDF 모듈을 사용하지 않을 경우 다음과 같은 가장 기본적인 설정이 남게 됩니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/algo-creation-2.png)

지금은 기본 설정에 대해 설명하겠습니다.

첫 번째 줄은 `class CalibratedUncoupledCoreWave(QCAlgorithm):`알고리즘을 생성합니다.

이름은 `CalibratedUncoupledCoreWave`임의적이며 원하는 대로 변경할 수 있습니다. QuantConnect는 재미있는 이름을 제공하는 것을 좋아합니다.

중요한 부분은 알고리즘이 클래스에서 상속되어 `QCAlgorithm`메서드와 변수를 사용할 수 있다는 점입니다. 따라서 이 비트를 변경하지 마세요.


### 초기화 및 OnData 메서드

`def Initialize(self):`및 메소드 `def OnData(self, data):`는 항상 알고리즘에 존재합니다.

물론 자신만의 추가 메서드/함수를 작성하고 특정 시간에 활성화되도록 할 수도 있습니다. 진행하면서 설명하겠습니다 `Initialize()`!`OnData()`

#### 초기화()

`def Initialize(self):`백테스팅/실시간 거래가 시작되기 전에 실행됩니다. 여기서는 중요한 변수, 모듈을 설정하고 데이터를 추가하고 표시기를 준비하는 등의 작업을 수행합니다.

또한 **예약된 이벤트를** 사용 하여 `Initialize()`하루 중 특정 시간에 실행되는 코드를 트리거할 수도 있습니다.

![[Pasted image 20230928161735.png]]

#### 날짜 및 현금 설정

여기서 우리는 그것이 가지고 있는 `self.SetStartDate(2018, 4, 1)`것과 `self.SetCash(100000)`방법들을 볼 수 있습니다. 이는 백테스트 시작 날짜와 알고리즘에 할당된 현금을 설정합니다.

`self.SetEndDate()`백테스트의 종료 날짜를 결정하기 위해 추가할 수도 있습니다 . 설정하지 않으면 기본적으로 현재 날짜까지 백테스트가 실행됩니다.

```python
def Initialize(self):
    self.SetStartDate(2018, 4, 1)  # Set Start Date
    self.SetEndDate(2020, 4, 1)  # Set End Date
    self.SetCash(100000)  # Set Strategy Cash
```

`SetStartDate()``SetEndDate()`명백한 이유로 실시간 거래 중에는 무시됩니다 .

#### 데이터 추가

또한 메소드 내에 데이터를 추가합니다 `Initialize()`.

이를 수행하는 일반적인 템플릿은 매우 간단합니다.

`self.AddEquity()`주식의 경우 SPY와 같이 향후 사용을 위해 내부적으로 할당할 수 있는 보안 개체를 반환하는 데 사용합니다 .

```python
self.spy = self.AddEquity("SPY", Resolution.Hour, Market.Oanda)
```

`Resolution`는 데이터 막대의 기간이며 주식에 대한 기본 옵션은 다음과 같습니다.

- Resolution.Tick
- Resolution.Second
- Resolution.Minute
- Resolution.Hour
- Resolution.Daily

`Market`여러 시장이 동일한 자산을 추적하고 특정 시장에서 데이터를 가져오려는 경우 매개변수는 데이터를 가져오는 시장을 나타냅니다 . QuantConnect에는 아무것도 지정하지 않을 경우 각 자산에 사용되는 기본 시장이 있습니다.

다음도 있습니다:

- AddForex() --추가외환
- AddCrypto()
- AddCfd()
- AddOption()
- AddFuture()

모두 매우 유사하게 동작하는 해당 자산 클래스에 대한 방법입니다.

모든 메소드에는 종종 무시될 수 있는 좀 더 특수화된 매개변수가 있으며, 그 중 순열이 너무 많아 이 가이드 전체에서 사용하는 각 메소드를 간결하게 나열할 수 없습니다.

사용 가능한 기능에 대한 전체 개요를 보려면 터미널 오른쪽 패널에서 "API"를 클릭하고 아래와 같이 관련 방법/용어를 검색하세요.

![[Pasted image 20230928162216.png]]

#### 표시기 설정

`Initialize()`또한 RSI 또는 MACD와 같이 의 주요 알고리즘에 사용하려는 지표를 설정했습니다 .

예를 들어 RSI 지표의 경우 되돌아보기 기간, 과매수 및 과매도 수준과 같은 주요 변수를 설정하고 `self`알고리즘의 다양한 방법에서 참조할 수 있도록 설정하는 것을 기억합니다.

```python
RSI_Period    = 14            # RSI Look back period 
self.RSI_OB   = 60            # RSI Overbought level
self.RSI_OS   = 40            # RSI Oversold level
```

그런 다음 원하는 RSI 조회 기간을 사용하여 SPY에 대한 RSI 표시기 개체(QCALgorithm 클래스에서 상속됨)를 설정합니다.

```python
self.RSI_Ind_SPY = self.RSI("SPY", RSI_Period)
```


#### 예열 기간 설정

또한 기술 지표, 과거 데이터 배열 등과 같은 구성 요소가 기본 알고리즘이 활성화되기 전에 준비되거나 채워질 수 있도록 "준비" 기간을 설정할 수도 있습니다. 워밍업 기간 동안에는 거래가 실행되지 않습니다.

그렇게 하려면 `SetWarmUp()`아래에 표시된 방법을 사용하십시오.

```python
self.SetWarmUp(200) # Warm up 200 bars for all subscribed data.
self.SetWarmUp(timedelta(7)) # Warm up 7 days of data.

# Or perhaps ensure that the RSI indicator has enough data before trading. 
self.SetWarmUp(RSI_Period)
```

또한 알고리즘은 부울을 사용하여 `IsWarmingUp`워밍업 기간이 완료되었는지 확인할 수 있습니다.

#### 예정된 이벤트

**알고리즘이 Scheduled Events** 를 통해 데이터 업데이트를 수신하는 시간과 관계없이 하루 중 특정 시간에 실행되도록 코드 블록(메서드/함수)을 예약할 수 있습니다 .

**예약된 이벤트에는** 실행할 함수/메서드와 함께 이벤트가 실행되는 시기를 지정하고 내부로 이동하는 날짜 및 시간 규칙이 필요합니다 `Initialize()`.

이벤트를 예약하는 방법은 입니다 `self.Schedule.On(DateRule, TimeRule, Action)`.

**다음은 DateRules** 및 **TimeRules 의** 몇 가지 예입니다 .

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/scheduled-events-rules.png)

전체 목록을 보려면 [예정된 이벤트](https://www.quantconnect.com/docs/algorithm-reference/scheduled-events) 문서로 이동하여 DateRule 및 TimeRule 문서를 확장하세요.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/date-and-timerule-small.png)


다음은 먼저 매일 실행되도록 설정된 예약된 이벤트의 예이며, 더 구체적으로는 매일 10분마다 실행됩니다. 메서드/함수 self.ExampleFunc를 설정합니다. 이는 우리가 원하는 모든 것이 될 수 있습니다.

```python
self.Schedule.On(self.DateRules.EveryDay(),  
                 self.TimeRules.Every(timedelta(minutes=10)), 
                 self.ExampleFunc)
```

`Initialize()`요약하면, 방금 배운 여러 기능을 채워넣은 알고리즘 구조는 다음과 같습니다 .

![[Pasted image 20230928162752.png]]

### 온데이터()

![](https://cdn.shortpixel.ai/spai/q_lossy+w_695+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/ondata.png)

`def OnData(self, data):`새로운 데이터가 알고리즘에 전달될 때마다 활성화되므로 에서 요청한 데이터 해상도에 따라 매시간, 매일 또는 매주 등이 될 수 있습니다 `Initialization(self)`.

여기에서 거래 논리를 실행하거나 지표 또는 데이터 프레임을 업데이트할 수 있습니다.

**예약된 이벤트를** 사용하면 데이터 업데이트와 관련되지 않은 정기적인 시간 간격/특정 이벤트에 대한 기능을 활성화할 수도 있습니다 .

또한 해당 시간대에 실행되는 QuantConnect와 같거나 내장된 `OnHour()`다른 기능도 있습니다 . `OnEndOfDay()`가이드가 계속해서 관리가 가능하도록 이러한 기능을 점진적으로 소개할 예정입니다.

#### 백테스팅과 실시간 거래

![](https://cdn.shortpixel.ai/spai/q_lossy+w_673+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/go-live-and-backtest.png)

백테스팅과 실시간 거래를 위한 코드 작성은 똑같습니다. 모두 main.py 패널에 들어갑니다.

백테스트를 수행하려면 최소한 `SetStartDate()`및 `SetCash()`변수가 설정된 상태에서 "백테스트" 버튼을 누르기만 하면 됩니다.

라이브 거래를 시작하려면 "Go Live"를 누른 다음 계정이 있는 중개업체를 선택하고(또는 종이 거래를 선택) 데이터 소스와 배포하려는 거래 노드를 선택해야 합니다.

귀하의 계정에 연결하려면 중개업체에 따라 계정 사용자 이름과 비밀번호 및/또는 API 키가 필요하며, 거래할 계정에 약간의 자금도 필요합니다!

또한 `self.LiveMode()`알고리즘이 라이브인지 확인하는 데 사용할 수 있는 유용한 부울이 있다는 점에 유의하세요. 예를 들어:

```python
if self.LiveMode:
      # execute this code only if algorithm is in live trading mode
```


#### 연구(Jupyter 노트북)

마지막으로 QuantConnect에는 프로젝트 내에서 액세스할 수 있는 내부 Jupyter 노트북 환경이 함께 제공됩니다.

이는 데이터 탐색에 유용할 수 있습니다. 이 가이드의 뒷부분에서 과거 및 기본 데이터를 가져오고 시각화하는 방법을 보여주기 위해 사용할 것입니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/research-notebook.png)

## QuantConnect의 기본 백테스팅 작업은 무엇입니까?

**_이러한 방법은 주로 클래식 백테스팅 방법을 의미합니다._**

### QuantConnect를 사용하여 어떻게 주문할 수 있나요?

QuantConnect를 사용하면 다양한 주문을 할 수 있습니다.

다음은 이용 가능한 다양한 주문 유형과 각 주문에 제공해야 하는 주요 매개변수에 대한 개요입니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_657+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/order-types-1.png)

모든 주문은 주문 상태를 쿼리하고 업데이트하거나 취소하는 데 사용할 수 있는 **OrderTicket 개체를 반환합니다. 방법은 다음 섹션에서 설명하겠습니다!**

```python
# marketOrderTicket is the OrderTicket object returned for our market order 
marketOrderTicket = self.MarketOrder("SPY", 100)
```

**시장 주문은** 즉시 실행되며 현재 시장 가격부터 시작하여 채워질 때까지 주문서를 위아래로 구매하므로 유동성이 적은 시장에서 대규모 주문이 발생할 경우 잠재적인 하락 가능성에 유의하세요.

시장가 주문은 이론적으로 거의 즉시 실행되기 때문에 이를 취소하거나 업데이트할 가능성이 거의 없습니다.

그러나 marketOrderTicket 개체를 사용하여 다음과 같이 시장 개체의 평균 채우기 가격을 확인할 수 있습니다.

```python
 # Check the average fill price of your market order using your OrderTicket
self.Debug("Market Order Fill Price: {0}".format(marketOrderTicket .AverageFillPrice))
```

QuantConnect 터미널에 있는 모든 코드는 주문이 체결될 시간을 주기 위해 시장 주문을 실행한 후 **5초 동안 일시 중지 됩니다.**

이 일시 중지 기간을 조정하려면 다음 코드 줄을 사용하여 원하는 대로 초 값을 변경하세요.

```python
# Adjust the market fill-timeout to 10 seconds.
self.Transactions.MarketOrderFillTimeout = timedelta(seconds=10)
```

`True`한 번에 많은 수의 거래를 실행하고 각 거래에 대한 응답을 기다리지 않으려면 시장 주문에 매개변수를 추가하여 비동기적으로(지연 없이) 실행되도록 설정할 수도 있습니다.

```python
# Create a Market Order for 100 shares of SPY asynchronously 
self.MarketOrder("SPY", 100, True)
```

_구매 대신 판매_ 하려면 다음과 같이 **음수 수량을** 사용해야 합니다 .

```python
# Create a Market Order to sell 100 shares of SPY asynchronously 
self.MarketOrder("SPY", -100, True)
```

**지정가 주문은** 즉시 체결되지 않고 지정된 매수 또는 매도 가격에 도달한 경우에만 체결됩니다.

다음은 현재 가격(마지막 데이터 막대의 종가보다 5% 아래)에 실행되는 지정가 주문을 실행하는 방법의 예입니다.

```python
# Purchase 10 SPY shares when its 5% below the current price
close = self.Securities["SPY"].Close
limitTicket = self.LimitOrder("SPY", 10, close * .95)
```

### QuantConnect를 사용하여 어떻게 손절매를 설정하고 이익을 얻을 수 있나요?

#### 정지 손실

불행하게도 QuantConnect는 추적 중지 손실의 사용을 허용하지 않습니다.

그렇긴 하지만, 우리는 과도한 하락으로부터 우리를 보호하기 위해 여전히 표준 정지 손실을 설정할 수 있습니다.

이를 위해 우리는 `StopMarketOrder(symbol, quantity, price)`방법을 사용합니다.

_구매 대신 판매 하려면_ **음수 수량을** 사용해야 한다는 점을 기억하세요 (이는 모든 다른 주문 유형에 해당됩니다).

예를 들어, 가격이 18달러 이하로 떨어지면 IBM 주식 10주를 시장에서 매도하기 위해 손절매를 설정할 수 있는 방법은 다음과 같습니다.

```python
stopMarketTicket = self.StopMarketOrder("IBM", -10, 18)
```

그리고 이것은 현재 가격보다 5% 낮은 SPY 10주를 구매하도록 지정가 주문을 설정하고, 하락으로부터 우리 자신을 보호하기 위해 지정가 구매보다 3% 더 낮은 가격으로 10주 모두에 대한 시장 정지 손실을 설정할 수 있는 방법의 예입니다.

```python
# Purchase 10 SPY shares when its 5% below the current price
current_price= self.Securities["SPY"].Close
limitTicket = self.LimitOrder("SPY", 10, current_price* .95)

# And set stop loss 3% below purchase price
stopMarketTicket = self.StopMarketOrder("SPY", -10, current_price* 0.95*0.97)
```

#### 이익실현

자산의 가치가 매수 포인트에서 미리 결정된 금액만큼 상승하면 이익을 얻기 위해 _제한 판매 주문을_ 설정하려고 합니다 .

다음은 SPY 10주에 대해 $350의 이익실현을 설정할 수 있는 방법입니다( _음수 수량을_ 다시 기억하세요 ).

```python
limitTicket = self.LimitOrder("SPY", -10, 350)
```

이전 예를 계속하면 다음과 같이 SPY 10주의 한도 매수에 각각 절반을 5%, 10% 더 높은 이익실현을 추가할 수 있으며 보호적 손절매 3% 아래에 추가할 수 있습니다.

```python
# Purchase 10 SPY shares when its 5% below the current price
current_price= self.Securities["SPY"].Close
limitTicket = self.LimitOrder("SPY", 10, current_price* .95)

# Set stop loss 3% below purchase price
stopMarketTicket = self.StopMarketOrder("SPY", -10, current_price* 0.95*0.97)

# And set take profits 5% and 10% above purchase price
tp1Ticket = self.LimitOrder("SPY", -5, current_price*1.05)
tp2Ticket = self.LimitOrder("SPY", -5, current_price*1.1)
```

실제로는 이익 실현 중 하나에 도달하면 정지 손실을 업데이트하거나 삭제하고, 정지 손실에 도달하면 이익 실현을 삭제하고 싶을 것입니다. 다음 섹션에서 그 방법을 보여드리겠습니다!


### QuantConnect를 사용하여 어떻게 주문을 취소하거나 포트폴리오를 청산할 수 있나요?

#### 주문 취소 중

`Cancel(optionalDescriptiveTextString)`OrderTicket 객체의 메소드를 사용하여 간단히 주문을 취소할 수 있습니다 .

다음은 지정가 매수 주문을 설정하고 나중에 취소하기로 결정하는 방법입니다.

```python
# Create an order and save its ticket
limitTicket = self.LimitOrder("SPY", 10, current_price* .95)

# Cancel order and save response
response = limitTicket.Cancel("Cancelled SPY Trade")
```

OrderTicket 반환을 조정하는 OrderResponse 개체를 사용하여 `response`변경이 성공했는지 확인할 수 있습니다.

```python
# Use order response object to read status
if response.IsSuccessful:
     self.Debug("Order successfully cancelled")
```

또한 다음을 사용하여 열려 있는 모든 주문을 취소할 수 있습니다 `Self.Transactions.CancelOpenOrders()`.

```python
# Cancel all open orders
allCancelledOrders = self.Transactions.CancelOpenOrders()
```

`CancelOpenOrders()`또는 다음과 같이 문자열을 에 제공하여 특정 자산과 관련된 모든 미결 주문을 취소할 수 있습니다 .

```python
# Cancel orders related to SPY
spyCancelledOrders = self.Transactions.CancelOpenOrders("SPY")
```

예를 들어 이전 예를 확장하면 정지 손실이 발생하면 SPY에 대해 남아 있는 모든 미결 주문(이 시점에서 이익 실현 제한 주문이 됨)을 취소하여 상황을 정리할 수 있습니다. OCA/One-을 시뮬레이션할 수 있습니다 **. 취소 - 모든** 주문 스타일을 순회합니다(QuantConnect는 직접적인 OCA 주문을 허용하지 않습니다).

#### 청산

다음과 같이 포트폴리오의 특정 자산 전체 또는 포트폴리오 전체를 즉시 **청산** 할 수도 있습니다 .`self.Liquidate(optionalAssetString)`

```python
# Liquidate all SPY in your portfolio
self.Liquidate("IBM")

# Liquidate entire portfolio
self.Liquidate()
```

이 두 가지 모두 자산/전체 포트폴리오에 대한 **모든 미결제 주문을 취소한** 다음 자산/전체 포트폴리오 보유 자산에 대한 **시장 매도 주문을 생성하여 기록적인 속도로 100% 현금으로 반환됩니다.**

### QuantConnect를 사용하여 주문을 어떻게 업데이트할 수 있나요?

주문을 업데이트하려면 OrderTicket을 사용해야 합니다.

주문의 다음 속성을 업데이트할 수 있습니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_651+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/updating-orders.png)

OrderTicket의 메소드 에 **UpdateOrderFields** 객체를 전달하여 주문이 업데이트됩니다 .`Update()`

주문을 생성한 다음 업데이트하겠습니다.

```python
# Create an order
limitTicket = self.LimitOrder("SPY", 10, 221)
```

주문을 업데이트하려면 먼저 UpdateOrdersField 객체를 생성하세요.

```python
# Create an UpdateOrderFields object
updateSettings = UpdateOrderFields()
```

일부 주문 매개변수를 업데이트합니다.

```python
updateSettings.LimitPrice = 219
updateSettings.Quantity= 15
```

그런 다음 채워진 UpdateOrderFields 개체를 주문 티켓의 Update 메서드에 전달합니다. 그러면 업데이트가 성공했는지 확인하는 데 사용할 수 있는 OrderResponse가 다시 생성됩니다.

```python
response = limitTicket.Update(updateSettings)

# Validate the response is OK
if response.IsSuccessful:
     self.Debug("Order updated successfully")
```

이제 QuantConnect의 주문 배치 및 관리 시스템의 주요 기능 중 일부를 살펴보았습니다. 가능한 기능에 대한 전체 개요는 [_거래 및 주문_ 문서를](https://www.quantconnect.com/docs/algorithm-reference/trading-and-orders) 확인하세요 !

### QuantConnect를 사용하여 과거 데이터를 어떻게 얻을 수 있나요?

첫째, 터미널의 알고리즘이나 연구 노트북에서 직접 과거 데이터에 액세스할 수 있다는 점에 유의하는 것이 중요합니다.

두 경우 모두 메서드를 사용하며 `History(symbol[], time period/bar period/start + end time period, resolution = null)`기록 데이터는 Pandas 데이터 프레임에 반환됩니다.

- **Symbol[]은** 단일 문자열이거나 문자열 목록일 수 있습니다.
- **기간/막대 기간/시작 + 종료 기간은** QuantConnect의 API를 사용하여 세 가지 다른 방식으로 기간을 표현할 수 있기 때문에 약간 혼란스럽습니다. 잠시 후에 몇 가지 예를 들어보겠습니다!
- **해상도** 는 데이터 프레임(분/시간/일 등)의 데이터 막대/행의 기간입니다.

#### 터미널/알고리즘에서:

먼저 자산 데이터를 구독합니다.

```python
self.AddEquity("SPY", Resolution.Daily)
```

그런 다음 이 `History()`메서드를 사용하여 원하는 세 가지 기간 옵션으로 pandas 데이터 프레임을 반환합니다.

```python
# Returns the past 10 days of historical hourly data
self.df= self.History(self.Symbol("SPY"), timedelta(days=10), Resolution.Hour)
```

```python
# Returns the past 10 bars of historical hourly data
self.df= self.History(self.Symbol("SPY"), 10, Resolution.Hour)
```

```python
start_time = datetime(2019, 1, 1) # start datetime for history call
end_time = datetime(2020, 1, 1) # end datetime for history call

# Returns hourly historical data between January 1st 2019 and January 1st 2020
self.df= self.History(self.Symbol("SPY"), start_time, end_time, Resolution.Hour)
```

#### 연구 노트에서:

self를 참조하는 대신 노트북에 **QuantBook() 개체를 생성한 다음 이를 참조해야 한다는 점을 제외하면 매우 유사합니다.**

```python
# Create QuantBook() object
qb = QuantBook()

# Subscripe to SPY data
spy = qb.AddEquity("SPY", Resolution.Daily)
```

유일한 차이점은 QCALgorithm 객체가 아닌 독립형 노트북에 있기 때문에 `Self.`앞이 필요하지 않고 대신 `df`참조한다는 것입니다.`spy.Symbol``self.Symbol("SPY")`

```python
# Returns the past 10 days of historical hourly data
df = qb.History(spy.Symbol, timedelta(days=10), Resolution.Hour)
```

이제 우리가 터미널/알고리즘 내부로 돌아왔다고 가정하고 과거 데이터로 수행할 수 있는 몇 가지 다른 작업을 보여드리겠습니다.

#### 데이터프레임의 여러 티커

동일한 데이터 프레임에서 두 개 이상의 티커 데이터에 액세스할 수 있습니다.

```python
# Subscribe to data from multiple tickers
self.AddEquity("IBM", Resolution.Daily)
self.AddEquity("AAPL", Resolution.Daily)

# Set start and end time.
start_time = datetime(2019, 04, 25) # start datetime for history call
end_time = datetime(2020, 04, 27) # end datetime for history call

self.dataframe = self.History([self.Symbol("IBM"), self.Symbol("AAPL")], start_time, end_time)
```

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/multiple-tickers-in-a-dataframe.png)

_해상도_ 를 선택하지 않았기 때문에 QuantConnect의 API는 일일 증권에 대한 기본값을 사용했습니다.

#### 티커를 열로 변환하고 속성별로 비교하기

또한 티커를 열로 변환하고 단일 속성을 선택하여 다음을 사용하여 각 막대 기간의 해당 속성에 대해 쉽게 나란히 비교할 수 있습니다 `unstack(level=0)`.

```python
# Transforming using unstack and comparing tickers by "close" value
self.dataframe["close"].unstack(level=0)
```

![](https://cdn.shortpixel.ai/spai/q_lossy+w_293+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/unstack-for-single-attribute-historical-dataframe.png)

AAPL과 IBM의 일일 "종가" 가격 비교

### QuantConnect를 사용하여 기본 데이터를 어떻게 얻을 수 있나요?

불행하게도 QuantConnect는 알고리즘 내의 기본 과거 데이터에 대한 직접적인 액세스를 제공하지 않습니다.

즉, 알고리즘에서 SDF의 Coarse 및 Fine Universe 선택 모듈을 사용하여 현재 기본 데이터를 기반으로 원하는 자산을 필터링할 수 있습니다.

또한, 리서치 노트에서 역사적 기본 데이터에 접근할 수 있습니다. 그렇게 합시다!

#### GetFundamental()

역사적인 기본 데이터를 얻기 위해 우리는 항상 방법을 사용할 것입니다   `qb.GetFundamental(Symbols, Selector, StartDate, EndDate)`.

`History()`기호, StartDate 및 EndDate는 방금 사용한 방법 처럼 동작합니다 .

StartDate 및 EndDate를 지정하지 않으면 QuantBook은 1998년 1월 1일부터 모든 기본 데이터를 가져옵니다.

`Selector`기본 데이터의 특정 부분을 선택하는 방법입니다. 가능한 엄청난 범위의 선택기를 보려면 [QuantConnect 데이터 라이브러리의 기본 섹션을](https://www.quantconnect.com/docs/data-library/fundamentals) 확인하세요 .

#### P/E 비율 - 데이터프레임당 여러 티커

**ValuationRatios.PERatio** 선택기를 사용하여 일부 주식의 가격이 얼마나 적절한지 평가해 보겠습니다.

먼저 몇 가지 기호를 구독해 보겠습니다.

```python
qb = QuantBook()
amzn = qb.AddEquity("AMZN")
goog = qb.AddEquity("GOOG")
ibm = qb.AddEquity("IBM")
```

그런 다음 시작 날짜와 종료 날짜를 추가하고 `GetFundamental()`ValuationRatios.PERatio 선택기를 사용하여 메서드를 호출합니다.

```python
start_time = datetime(2020, 1, 1) # January 1st 2020
end_time = datetime.now() # Today's date

# Get the PE ratio for all securities between given dates
pe_history = qb.GetFundamental(qb.Securities.Keys, "ValuationRatios.PERatio", start_time, end_time)

pe_history
```

그 모습은 다음과 같습니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/pe-ratios.png)

다음을 사용하여 시각화를 더 쉽게 만들기 위해 시간에 따른 P/E 비율을 표시할 수 있습니다.

```python
# Plot PE ratios
pe_history.plot(figsize=(16, 8), title="PE Ratio Over Time")
plt.xlabel("Time")
plt.ylabel("PE Ratio")
plt.show()
```

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/plotted-pe-ratios.png)

또는 다음과 같이 검색된 기간 동안의 평균 p/e 비율을 기준으로 주식 목록을 정렬할 수 있습니다.

```python
# Sort stocks by their average PE ratio
sorted_by_mean_pe = pe_history.mean().sort_values()
sorted_by_mean_pe
```

```
IBM R735QTJ8XC9X       12.942418
GOOCV VP83T1ZUHROL     29.339131
AMZN R735QTJ8XC9X     107.074606
dtype: float64
```

물론 이것은 훨씬 더 많은 주식 목록을 가지고 있으면 훨씬 더 유용할 것입니다!

마지막으로 다음과 같이 데이터프레임에서 대괄호로 묶인 해당 티커를 간단히 참조하여 단일 티커의 결과만 표시하도록 데이터프레임을 필터링할 수 있습니다.

```python
pe_history["AMZN R735QTJ8XC9X"]
```

![](https://cdn.shortpixel.ai/spai/q_lossy+w_649+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/amazon-dataframe.png)

여기서 ValuationRatios.PERatio와 동일한 프로세스를 사용하여 다른 기본 데이터를 완전히 조사할 수 있습니다. 선택기를 변경하기만 하면 됩니다!

## QuantConnect에서 전략을 생성하고 백테스트하는 방법은 무엇입니까?

### 우리의 첫 번째 전략! 돈육 선물의 평균 회귀(전통적인 백테스팅)

이제 지금까지 배운 모든 내용을 결합하여 처음부터 기본 알고리즘 구축(SDF 모듈 사용 없음)을 시연한 다음 이를 백테스트해 보겠습니다.

우리는 돈육 선물에 대해 기본적인 평균 회귀 전략을 사용할 것입니다.

전략은 최근 가격의 이동 평균을 모니터링하고 가격이 최근 평균보다 크게 떨어지면 매수하고 크게 상승하면 매도하는 것입니다.

전체 추세가 계속 유지되더라도 추세선에서 상당한 편차가 어느 방향으로든 일시적일 가능성이 높다는 개념입니다.

이러한 전략은 다소 "소음 차익거래"로 간주될 수 있습니다.

이 예는 교육 목적으로만 사용되었습니다. 이 전략을 잘 이해하지 않는 한 실시간으로 실행하지 않는 것이 좋습니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/thumbnail_lean-hogs-1.png)

**이를 달성하기 위해 볼린저 밴드(Bollinger Bands)를** 사용합니다 .

**볼린저 밴드(Bollinger Band)는** 이동 평균 가격보다 X 표준 편차만큼 높은 가격 밴드입니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/bollinger-bands.png)

볼린저 밴드

이 예에서는 최근 가격 평균의 2 표준 편차보다 높거나 낮은 가격을 매수 및 매도 신호로 사용하지만 실제로는 가격이 볼린저밴드는 **90~95% 정도를 나타냅니다** .

가격이 볼린저 밴드에 너무 자주 도달하거나 초과하면 잘못된 신호를 많이 받을 수 있습니다.

가격이 충분히 도달하지 않으면 의미 있는 양의 거래를 할 수 없으며 실제로 시장이 극단적인 상황에 있을 때만 거래가 시작되어 가격이 계속해서 밴드 아래로 떨어지거나 밴드 위로 솟아오르게 될 수 있습니다. 이미 최근 평균과는 상당한 차이가 있습니다.

QuantConnect의 터미널에서 QCALgorithm에는 미리 코딩된 Bollinger Band 개체가 있습니다 `BB(symbol, lookbackPeriod, standardDeviations, movingAverageType, Resolution)`.

- **기호** : 데이터를 차트로 표시하려는 자산의 문자열
- **lookbackPeriod** : 이동 평균을 계산하는 데 사용할 기간(해상도 측면에서)
- **StandardDeviations** : 볼린저 밴드를 계산하기 위한 이동평균 위아래 표준편차의 양
- **MovingAverageType** : 사용할 이동 평균 유형(단순, 지수 등)
- **해상도** : 가격 데이터에 사용할 막대 기간(분, 시간, 일별 등)

#### 구현

이제 QuantConnect에서 평균 회귀 전략을 구축해 보겠습니다!

**먼저 QCALgorithm** 클래스 에서 언제나처럼 상속받아 알고리즘을 만들고 함수를 설정해 보겠습니다 `Initialize()`.

```python
import pandas as pd


class LeanHogsBollingerBandsAlgorithm(QCAlgorithm):

    def Initialize(self):
        
        self.SetStartDate(2015, 1, 1)    #Set Start Date
        self.SetEndDate(2020, 6, 1)      #Set End Date
        self.SetCash(100000)             #Set Strategy Cash
```

나중에 사용할 것이기 때문에 코드 시작 부분에서 팬더를 가져왔고 볼린저 밴드 표시기를 수동으로 워밍업할 것이기 때문에 **워밍업 기간을 설정하지 않았습니다.**

또한 알고리즘 전반에 걸쳐 사용할 플래그와 특정 선물 계약을 저장하는 데 사용할 할당되지 않은 `Initialize()`객체 를 추가해야 합니다 .`self.new_day``self.contract`

```python
self.new_day = True
self.contract = None
```

그런 다음 접근자 코드가 있는 린 호그의 미래 체인 데이터를 구독해야 합니다 `Futures.Meats.LeanHogs`.

```python
# Subscribe and set our expiry filter for the futures chain
futureES = self.AddFuture(Futures.Meats.LeanHogs)
```

**_선물_** 거래 는 일반 주식 거래보다 조금 더 복잡합니다.

_옵션_ 과 유사하게 선물 계약은 미래에 합의된 가격으로 자산을 구매하거나 판매하기로 한 계약을 나타냅니다.

그러나 옵션과 달리 계약 소유자는 미래 날짜에 합의된 가격으로 자산을 매매해야 하는 반면, 옵션은 소유자에게 그렇게 할 권리가 있지만 의무는 부여하지 않습니다 _._

따라서 기본 자산에는 언제든지 유통되는 여러 선물 계약이 있는 경향이 있으며, 각각의 선물 계약은 미래에 대해 서로 다른 만료 날짜를 갖습니다. 따라서 선물을 거래할 때는 거래할 특정 계약(만기일)을 선택해야 합니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/futures-chain.png)

선물 데이터를 구독하면 일반적인 가격 데이터가 제공되는 것이 아니라 다양한 계약에 대한 정보 모음인 **FuturesChain이 제공됩니다.**

QuantConnect에서 **FuturesChain** 객체에는 귀하가 구독한 모든 다양한 선물에 대한 체인이 포함되어 있습니다(예: 금 선물용 체인 1개, 돈육 선물용 체인 1개, 비트코인 ​​선물용 체인 1개 등).

다음과 같이 FutureChain 개체를 반복하여 개별 미래에 대한 계약 체인에 액세스할 수 있습니다.

```python
for chain in slice.FutureChains.Values:
    #do something with the specific chain
```

여기에서는 돈육 선물만 구독했기 때문에 FutureChain 개체에는 돈육 선물 체인만 있습니다.

일반적으로 다음과 같이 미래 계약 체인을 탐색할 수 있습니다.

```python
# Explore the future contract chain
def OnData(self, slice):
    for chain in slice.FutureChains.Values:
        contracts = chain.Contracts
        for contract in contracts.Values:
            # do something with specific contract
```

특정 선물 계약에는 다음과 같은 속성이 있습니다.

```python
class FuturesContract:
    self.Symbol # (Symbol) Symbol for contract needed to trade.
    self.UnderlyingSymbol # (Symbol) Underlying futures asset.
    self.Expiry # (datetime) When the future expires
    self.OpenInterest # (decimal) Number of open interest.
    self.LastPrice # (decimal) Last sale price.
    self.Volume # (long) reported volume.
    self.BidPrice # (decimal) bid quote price.
    self.BidSize # (long) bid quote size.
    self.AskPrice # (decimal) ask quote price.
    self.AskSize # (long) ask quote size.
```

이것이 알고리즘에 대해 알아야 할 전부입니다. 그러나 선물에 대한 추가 정보는 [여기에서](https://www.quantconnect.com/docs/data-library/futures) 문서를 확인하세요 .

선물 계약은 지속적으로 존재하고 만료되기 때문에 거래할 특정 선물 계약을 선택하고 해당 계약의 포지션을 청산하고 정기적으로 새로운 계약으로 교체하기 위해 만료가 다가오는 시기를 알 수 있는 방법이 필요합니다.

만기일이 다가올수록 계약 가격이 현물 가격으로 수렴되기 때문에 만기일이 매우 가까운 선물 계약을 거래하는 것은 별 의미가 없습니다.

그렇기 때문에 그리고 우리는 새로운 계약으로 교체하기 전에 거래를 완료할 시간을 주고 싶다는 사실 때문에 **30일 이내에** 만료 되는 선물 계약을 구독하도록 필터를 설정했습니다 `Initialize()`.

또한 다음 데이터를 수신하려는 계약 만료 기간을 정의하기 위해 만료까지 상한을 1080일로 설정했습니다.

```python
futureES.SetFilter(TimeSpan.FromDays(30), TimeSpan.FromDays(1080))
```

우리는 알고리즘 외에 네 가지 다른 기능을 사용할 것입니다 `Initialize(self)`. 그들은 다음과 같습니다:

- `OnData(self, slice)`– 데이터가 수신될 때마다 실행됩니다(QuantConnect에 내장되어 있음)
- `InitUpdateContract(self, slice)`코드에서 누군가를 호출해야 합니다(사용자 정의).
- `OnHour(self, sender, bar)`– 매 시간마다 발생(내장)
- `OnEndOfDay(self)`– 매일 끝날 때 발생(내장)

다음과 같이 하루가 끝날 때마다 부울 값을 **True** 로 `OnEndOfDay()`설정하는 데 간단히 사용할 것이기 때문에 먼저 비켜갑시다 .`new_day`

```python
def OnEndOfDay(self):
    self.new_day = True
```

`InitUpdateContract()`이제 거래할 첫 번째 계약을 선택하고, 현재 계약이 만료되는지 확인하고, 그렇다면 새 계약으로 롤오버하는 가장 긴 기능인 에 대해 작업해 보겠습니다 .

첫째로, 새로운 날이 아니라면 계약이 여전히 괜찮고 롤오버할 필요가 없다고 가정하고 함수를 종료합니다. (기억하세요. self.new_day를 True로 설정했기 때문에 이 함수가 처음 `Initialize()`으로 이 검사를 통과한다고 합니다):

```python
def InitUpdateContract(self, slice):
    # Reset daily - everyday we check whether futures need to be rolled
    if not self.new_day:
        return 
```

이제 우리는 이미 계약을 거래하고 있는지, 만료일이 최소 3일 남았는지 확인합니다. 이 두 가지 사실이 모두 사실이라면 나머지 기능을 다시 건너뜁니다.

```python
if self.contract != None and (self.contract.Expiry - self.Time).days >= 3: # rolling 3 days before expiry
    return 
```

새로운 날이고 계약을 선택하지 않았거나 선택한 계약이 만료 3일 이내인 경우 백테스트 로그에 만료되는 계약의 이름과 자체를 사용하여 만료되어야 하는 기간을 인쇄합니다. .Log(“message”) 메소드를 사용하여 새 계약 거래를 준비하기 위해 현재 포지션을 청산합니다.

```python
for chain in slice.FutureChains.Values:
    # If we trading a contract, send to log how many days until the contract's expiry
    if self.contract != None:
        self.Log('Expiry days away {} - {}'.format((self.contract.Expiry-self.Time).days, self.contract.Expiry))
    
        # Reset any open positions based on a contract rollover.
        self.Log('RESET: closing all positions')
        self.Liquidate()        
```

그런 다음 미래 계약 체인에서 계약 목록을 가져와 먼저 새 계약을 선택합니다.

```python
# get list of contracts
contracts = list(chain.Contracts.Values)
chain_contracts = list(contracts) #[contract for contract in chain]
```

그런 다음 만료일을 기준으로 최신 것부터 가장 오래된 것 순으로 계약을 정렬합니다.

```python
# order list of contracts by expiry date: newest --> oldest
chain_contracts = sorted(chain_contracts, key=lambda x: x.Expiry)
```

그런 다음 해당 목록의 초기에 계약을 선택합니다(어쨌든 향후 30일 이내에 이러한 계약이 만료되지 않도록 이미 필터를 설정했음을 기억하십시오).

```python
# pick out contract and log contract name
self.contract = chain_contracts[1]
self.Log("Setting contract to: {}".format(self.contract.Symbol.Value))
```

QuantConnect의 선물 데이터는 **초** 및 **분 형식으로만 제공되며 시간별 시간 프레임에 대한 지표를 작성하려고 하기 때문에** **TradeBarConsildator를** 설정하여 분 데이터를 수집하고 이를 시간별 데이터로 묶습니다.

```python
# Set up consolidators.
one_hour = TradeBarConsolidator(TimeSpan.FromMinutes(60))
one_hour.DataConsolidated += self.OnHour
            
self.SubscriptionManager.AddConsolidator(self.contract.Symbol, one_hour)
```

간략하게 설명하고 주식 및 암호화폐 등을 거래할 때 일반적으로 더 유연한 데이터 해상도를 가지게 되므로 통합자가 작동하는 방식을 정확히 건너뛰겠습니다. 하지만 다른 용도로 사용자 정의 파일을 구축해야 한다면 QuantConnect [통합 데이터 문서](https://www.quantconnect.com/docs/algorithm-reference/consolidating-data) 에서 이에 대해 알아볼 수 있습니다 !

이제 선물 계약에 대한 시간별 데이터가 있으므로 BollingerBand 표시 개체를 초기화하겠습니다.

```python
# Set up indicator
 self.Bolband = self.BB(self.contract.Symbol, 50, 2, MovingAverageType.Simple, Resolution.Hour)
```

여기에서는 거래 중인 계약의 가격 데이터를 분석하도록 설정했습니다. 지난 50시간의 데이터를 사용하여 시간별 단순 이동 평균을 계산하고 이 이동 평균에서 +- 2 표준 편차의 볼린저 밴드를 생성합니다.

민감도(표준편차)를 무엇으로 설정해야 할지 알기 어려울 수 있지만, 호기심을 위해 볼린저 밴드를 +- 1.5 표준편차로 설정한 주간 돈육의 미래 데이터는 다음과 같습니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/1.5-weekly-bollbands.png)

우리는 주간 데이터 대신 시간별 데이터를 사용하여 거래하고 있기 때문에(그리고 짧은 기간은 변동성이 더 큰 경향이 있음) 표준 편차 임계값을 시작점으로 2로 올렸습니다.

이제 선물 계약에 대한 50시간(50*60분)의 과거 데이터를 수집하고 다음 방법을 사용하여 Bolband 표시기를 수동으로 워밍업합니다 `Update()`.

```python
history = self.History(self.contract.Symbol, 50*60, Resolution.Minute).reset_index(drop=False)
            
for bar in history.itertuples():
    if bar.time.minute == 0 and ((self.Time-bar.time)/pd.Timedelta(minutes=1)) >= 2:
    self.Bolband.Update(bar.time, bar.close)
```

오늘 거래 중인 계약을 이미 롤포워드하여 기능을 종료했기 때문에 이제 **False**`self.new_day` 로 설정했습니다 .`InitUpdateContract()`

```python
self.new_day = False
```

이제 우리의 기능을 다루겠습니다 `OnData()`.

이는 우리가 구독한 FuturesChain에 대한 새로운 데이터가 제공될 때마다 활성화됩니다.

따라서 이 함수가 실행될 때마다 우리는 `InitUpdateContract()`활성화된 계약의 상태를 확인하고, 필요한 경우 새 계약으로 롤오버하고(또는 알고리즘 시작 시 초기 계약을 선택하고) 이전 포지션을 청산하고 워밍업을 실행하려고 합니다. 새로운 볼린저밴드 지표:

```python
def OnData(self, slice):
    self.InitUpdateContract(slice)
```

`slice`활성화하는 새로운 데이터 개체가 수신되고 있습니다 `OnData()`.

마지막으로, 우리는 `OnHour(self, sender, bar)`QuantConnect에 내장된 기능을 사용하여 매 시간마다 거래 로직을 실행하기 위해 실행할 것입니다(우리는 시간 단위로 볼린저 밴드 지표도 구성했다는 것을 기억하십시오!).

먼저, 볼린저 밴드 지표가 초기화되었는지, 성공적으로 워밍업되었는지, 상호작용 중인 가격 데이터 막대가 실제로 거래하려는 계약에 대한 것인지 확인하고, 그렇다면 현재 가격을 추출합니다. 선물 계약의 경우:

```python
def OnHour(self, sender, bar):
    if (self.Bolband != None and self.Bolband.IsReady):
        if bar.Symbol == self.contract.Symbol:
            price = bar.Close
```

이전 if 문에서 계속해서 다음을 통해 현재 거래 중인 계약에 대해 보유하고 있는 계약 수를 확인합니다 `self.Portfolio[symbol].Quantity`.

```python
holdings = self.Portfolio[self.contract.Symbol].Quantity
```

포트폴리오 개체에 대해 좀 더 자세히 알아보고 포트폴리오 개체로 무엇을 할 수 있는지 알아보려면 [여기로](https://www.quantconnect.com/docs/algorithm-reference/securities-and-portfolio) 이동하세요 !

이제 마침내 거래 논리를 구현하겠습니다!

현재 거래 중인 계약을 보유하고 있지 않고 계약 가격이 볼린저 밴드 하한선 아래로 떨어지면 시장에서 2계약을 매수합니다.

```python
# buy if price closes below lower bollinger band
if holdings <= 0 and price < self.Bolband.LowerBand.Current.Value:
    self.Log("BUY >> {}".format(price))
    self.MarketOrder(self.contract.Symbol, 2)
```

이미 일부 계약을 보유하고 있고 가격이 볼린저 밴드 상단 위로 상승하면 모든 계약을 매도합니다(청산은 QuantConnect에서 시장 매도를 실행한다는 점을 기억하세요).

```python
# sell if price closes above the upper bollinger band
if holdings > 0 and price > self.Bolband.UpperBand.Current.Value:
    self.Log("SELL >> {}".format(price))
    self.Liquidate()
```

이것이 바로 우리가 선물에 대한 평균 회귀 전략을 실행하는 방법입니다!

기능을 마무리하기 위해 백테스트가 실행되는 동안 볼린저 밴드를 플롯하여 모든 것이 검사된 대로 작동하는지 시각적으로 확인할 것입니다.

```python
self.Plot("BB", "MiddleBand", self.Bolband.MiddleBand.Current.Value)
self.Plot("BB", "UpperBand", self.Bolband.UpperBand.Current.Value)
self.Plot("BB", "LowerBand", self.Bolband.LowerBand.Current.Value)
```

여기의 형식은 입니다 `Plot("name of chart to plot in", "name of specific line in chart", valueToPlot)`.

이 함수는 다음과 같은 경우 Bollinger 밴드가 아직 워밍업을 완료하지 않았음을 로그에 인쇄하기 위해 else 문을 사용하여 외부 if 수준에서 완료됩니다.

```python
else:
    self.Log('Bollinger Bands not ready yet')
```

조금 길고 복잡해 보일 수도 있지만 선물은 본질적으로 거래하기 까다로우며 QuantConnect의 유용한 개별 기능을 많이 다루었습니다!

전체적으로 최종 코드는 다음과 같아야 합니다.

```python
import pandas as pd


class LeanHogsBollingerBandsAlgorithm(QCAlgorithm):

    def Initialize(self):
        
        self.SetStartDate(2015, 1, 1)    #Set Start Date
        self.SetEndDate(2020, 6, 1)      #Set End Date
        self.SetCash(100000)             #Set Strategy Cash

        self.new_day = True
        self.contract = None
        
        
        # Subscribe and set our expiry filter for the futures chain
        futureES = self.AddFuture(Futures.Meats.LeanHogs)
        futureES.SetFilter(TimeSpan.FromDays(30), TimeSpan.FromDays(720))
        
        
    def OnData(self, slice):
        
        self.InitUpdateContract(slice)

    def InitUpdateContract(self, slice):
        # Reset daily - everyday we check whether futures need to be rolled
        if not self.new_day:
            return 
            
        if self.contract != None and (self.contract.Expiry - self.Time).days >= 3: # rolling 3 days before expiry
            return 
            
        for chain in slice.FutureChains.Values:
            # If we trading a contract, send to log how many days until the contract's expiry
            if self.contract != None:
                self.Log('Expiry days away {} - {}'.format((self.contract.Expiry-self.Time).days, self.contract.Expiry))
            
                # Reset any open positions based on a contract rollover.
                self.Log('RESET: closing all positions')
                self.Liquidate()
            
            # get list of contracts
            contracts = list(chain.Contracts.Values)
            chain_contracts = list(contracts) #[contract for contract in chain]
            # order list of contracts by expiry date: newest --> oldest
            chain_contracts = sorted(chain_contracts, key=lambda x: x.Expiry)
            
            # pick out contract and log contract name
            self.contract = chain_contracts[1]
            self.Log("Setting contract to: {}".format(self.contract.Symbol.Value))
            
            # Set up consolidators.
            one_hour = TradeBarConsolidator(TimeSpan.FromMinutes(60))
            one_hour.DataConsolidated += self.OnHour
            
            self.SubscriptionManager.AddConsolidator(self.contract.Symbol, one_hour)
            
            # Set up indicators
            self.Bolband = self.BB(self.contract.Symbol, 50, 2, MovingAverageType.Simple, Resolution.Hour)

            
            history = self.History(self.contract.Symbol, 50*60, Resolution.Minute).reset_index(drop=False)
            
            for bar in history.itertuples():
                if bar.time.minute == 0 and ((self.Time-bar.time)/pd.Timedelta(minutes=1)) >= 2:
                    self.Bolband.Update(bar.time, bar.close)
            
            self.new_day = False


    def OnHour(self, sender, bar):
        
        if (self.Bolband != None and self.Bolband.IsReady):
            if bar.Symbol == self.contract.Symbol:
                price = bar.Close
         
                holdings = self.Portfolio[self.contract.Symbol].Quantity
                
                # buy if price closes below lower bollinger band
                if holdings <= 0 and price < self.Bolband.LowerBand.Current.Value:
                    self.Log("BUY >> {}".format(price))
                    self.MarketOrder(self.contract.Symbol, 2)

                # sell if price closes above the upper bollinger band
                if holdings > 0 and price > self.Bolband.UpperBand.Current.Value:
                    self.Log("SELL >> {}".format(price))
                    self.Liquidate()
                        
            self.Plot("BB", "MiddleBand", self.Bolband.MiddleBand.Current.Value)
            self.Plot("BB", "UpperBand", self.Bolband.UpperBand.Current.Value)
            self.Plot("BB", "LowerBand", self.Bolband.LowerBand.Current.Value)
          
        else:
            self.Log('Bollinger Bands not ready yet')
                    
        
    def OnEndOfDay(self):
        self.new_day = True
```

이제 우리는 가장 흥미로운 부분인 백테스트를 진행할 수 있습니다!

**백테스트** 버튼을 누르면 백테스트가 초기화되기 시작합니다.

이 특정 백테스트를 완료하는 데 몇 분 정도 걸립니다. 그래프와 측정항목 업데이트를 실시간으로 보거나 완료되면 다시 돌아올 수 있습니다!

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/back-test-overview.png)

백테스트 결과!

보시다시피 우리 전략에는 약간의 기복이 있었지만 실제로는 5.62%의 수익률로 마무리했습니다. 많은 조정 없이는 나쁘지 않습니다!

오른쪽 상단 패널을 통해 보고 싶은 차트/측정항목을 선택할 수 있습니다. 우리가 그린 이 그래프는 기본적으로 표시되지 않으므로 "BB"를 수동으로 선택해야 합니다.

QuantConnect에 대해 주목할 점은 선물/옵션에 대한 벤치마크를 설정할 수 있고 코드에서 오류가 발생하지 않는 것처럼 보이지만 실제로는 작동하지 않으며 대신 관련 없는 항목의 벤치마크 그래프가 표시된다는 것입니다.

어쨌든 이것은 가격에 대한 볼린저 밴드의 모습입니다(실질적으로 우리 자신의 맞춤형 가상 벤치마크임). 우리는 매수 및 보유보다 확실히 더 나은 성과를 보이는 것을 볼 수 있습니다!

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/boll-bands.png)

마지막으로, 조금 아래로 스크롤하면 백테스트에 대한 자세한 통계를 확인할 수 있습니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/backtest-stats-overview.png)

실제 백테스트 주문 내역은 다음과 같습니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/backtest-orders.png)

주문 내역

그리고 로그 기록은 다음과 같습니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/backtest-logs-2048x954.png)

로그 기록

## QuantConnect의 전략 개발 프레임워크(SDF)란 무엇입니까?

우리는 QuantConnect의 SDF 모듈을 사용하지 않고 알고리즘을 구축했습니다.

이제 대신 SDF를 사용하여 알고리즘을 구축하겠습니다.

[우리는 여기서](https://algotrading101.com/learn/quantconnect-guide/#Strategy-Development-Framework) SDF가 무엇인지에 대해 이미 조금 이야기했습니다 .

요약하면 기본 흐름은 다음과 같습니다.

1. **유니버스 선택** (거래할 자산 선택)
2. **Alpha Creation** (거래 신호 생성)
3. **포트폴리오 구성** (보유 자산별 목표 설정)
4. **실행** (목표 달성을 위한 실행 방법)
5. **위험 관리** (성과가 좋지 않을 때 포트폴리오 요소를 청산하는 논리 설정)

알고리즘이 자동으로 올바르게 작동하려면 모든 모듈은 특정 형식의 개체를 체인의 다음 모듈에 전달해야 합니다.

처음에는 머리를 숙이는 데 많은 시간이 걸릴 수 있으므로 막히면 [여기에서 SDF 문서를 읽거나](https://www.quantconnect.com/docs/algorithm-framework/overview) [알고리즘 프레임워크 부트캠프를](https://www.quantconnect.com/terminal/#lesson-272/The-Algorithm-Framework) 통해 작업 할 수 있습니다 .

Universe Selection 모듈을 사용하는 예부터 시작해 보겠습니다.

### 1단계: QuantConnect의 Universe 선택 예시 사용: 기술주

먼저 '새 알고리즘 만들기'를 클릭하세요.

**그런 다음 우주** 섹션 까지 아래로 스크롤하여 사용 가능한 미리 만들어진 우주의 범위를 탐색하세요.

모듈을 클릭하면 해당 모듈이 어떻게 작동하는지, 어떤 조건을 기준으로 필터링하는지에 대한 설명이 제공됩니다.

제공되는 SDF 모듈은 언어로 Python을 선택했는지 C#을 선택했는지에 따라 조금씩 다릅니다.

우리는 "기술주" 모듈을 다루겠습니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/add-tech-stocks.png)

"모듈 추가"를 클릭하면 오른쪽 코드에 삽입됩니다.

보시다시피 **TechnologyUniverseModule.py 스크립트가** **main.py** 옆에 나타납니다 .

이 단계에서 이를 검토할 수 있지만 걱정하지 마십시오. 알고리즘 생성 프로세스가 완료되면 여전히 알고리즘 내에 있으며 편집할 수 있습니다.

기술 스톡 모듈은 다음과 같습니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/tech-stocks-dot-py-codfe.png)

QuantConnect의 알고리즘이 내부적으로 어떻게 설정되는지에 대해 많이 알지 않는 한 따라가기 어려운 많은 일이 일어나고 있지만 괜찮습니다. 모듈은 개입이 필요 없이 설명에 따라 작동합니다.

중요한 점은 모듈이 코드에 설명된 모든 다양한 조건(원하는 경우 자유롭게 조정할 수 있음)을 기준으로 주식을 필터링하고 거래할 주식 기호 목록을 Alpha Generation 모듈에 반환한다는 것입니다.

### 2단계: QuantConnect의 Alpha Creation 예제 사용: Smart Insider

#### 개요

알파 생성 모듈은 다른 많은 모듈이 단지 몇 가지 입력 매개변수만으로 자동으로 작동하기 때문에 모든 SDF 모듈 중에서 가장 수동 작업이 필요한 섹션일 것입니다. 그러나 종종 우리는 우리에게 제공되는 데이터를 Alpha Creation 모듈은 거래 로직을 작성하고 만족스러운 **통찰력을** 생성하여 포트폴리오 구성 모듈로 전달합니다.

하지만 이것이 항상 사실인 것은 아닙니다. 예를 들어 RSI 모듈과 같은 일부 지표는 추가 작업 없이 통찰력을 생성하지만 이러한 모듈 중 일부는 일부 포트폴리오 구성 모듈(예: InsightWeightingPortfolioConstructionModel)이 올바르게 작동하므로 바닐라 RSI Alpha 모듈을 이 포트폴리오 구성 모듈과 페어링하면 알고리즘이 실제로 거래를 하지 않습니다.

또한 알파 섹션은 둘 이상의 모듈을 추가할 수 있는 유일한 섹션입니다. 즉, 여러 알파 모듈의 알고리즘에서 한 번에 거래 통찰력을 얻을 수 있습니다.

이 전체 프로세스를 보여주기 위해 Alpha 모듈인 Smart Insider를 선택해 보겠습니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/smart-insider-1-2048x1142.png)

Smart Insider 모듈 코드는 다음과 같이 시작됩니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/smart-insider-orig-dot-py.png)

`OnSecuritiesChanged(self, algorithm, changes)`먼저 하단의 메소드를 다루겠습니다 .

그 목적은 Tech Stock 유니버스에 진입하는 새로운 주식에 대한 거래 및 의도 데이터를 구독하고, 떠나는 모든 주식에 대한 해당 데이터를 구독 취소하는 것입니다(유니버스의 모든 주식이 우리가 설정한 기준을 충족하도록 유니버스가 지속적으로 업데이트된다는 점을 기억하십시오).

`algorithm.Liquidate(security.Symbol)`현재로서는 거의 좋지만, 유니버스에서 제거된 모든 주식에서 포지션을 청산하기 위해 한 줄을 추가할 것입니다 .

이제 메서드 의 두 번째 부분은 `OnSecuritiesChanged()` 다음과 같습니다.

```python
## Remove SmartInsider Transaction and Intention data for each new equity
for security in changes.RemovedSecurities:
    if security.Type == SecurityType.Equity:
        algorithm.Liquidate(security.Symbol)
        transaction, intention = self.altDataSymbols.pop(security.Symbol, (None, None))
        algorithm.RemoveSecurity(transaction) if transaction is not None else None
        algorithm.RemoveSecurity(intention) if transaction is not None else None
```

이제 main 메소드를 살펴보겠습니다 `Update(self, algorithm, data)`.

#### 통찰력 생성

중요한 부분은 모든 Alpha 모듈이 **Insights 를** 반환해야 한다는 것입니다 .

Update 메소드는 Insight 객체의 배열을 반환합니다.

통찰력은   자산에 대한 _단일 예측입니다._

이는 가까운 미래에 자산 방향, 규모 및 신뢰도를 나타내는 실행 가능한 거래 신호로 간주될 수 있습니다. 모든 통찰력은 가중치 매개변수를 사용하여 통찰력에 대해 원하는 가중치를 설정할 수 있습니다.

통찰력에는 다음과 같은 속성이 있습니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/insight-attributes.png)

또한 선택적으로 가격이나 변동성 속성을 외부로 가져오고 다음과 같은 통찰력 개체를 생성할 수도 있습니다.

```python
# Skipping magnitude, confidence and source model and assigning 25% to weighting.
insight = Insight.Price("IBM", timedelta(minutes = 20), InsightDirection.Up, None, None, None, 0.25)
```

이는 대부분의 알고리즘에 대한 통찰력을 생성하는 데 충분하지만 통찰력 생성/알파 생성에 대해 자세히 알고 싶다면 [여기에서](https://www.quantconnect.com/docs/algorithm-framework/alpha-creation) 문서를 확인하세요 .

#### 구현

이제 우리는 **통찰력을** 창출 해야 하고 Smart Insider 데이터를 구독해야 한다는 것을 알고 있지만 이 데이터로 무엇을 해야 할지, 그것이 무엇인지는 정확히 명확하지 않습니다.

다행히 QuantConnect에는 Smart Insider 데이터에 대한 설명이 포함된 [대체 데이터 설명 영역이 있습니다.](https://www.quantconnect.com/docs/alternative-data/smart-insider#) 잠시 시간을 내어 잘 읽어보세요!

보시다시피 우리는 일부 거래 논리를 생성하고 **통찰력을 생성하기 위해** **의도** 및 **거래** 속성을 사용해야 합니다 .

여기서 시연을 위해 우리는 매우 기본적인 전략을 사용할 것입니다. 회사가 주식 환매 의사를 발표하면 **일시적인** 매수 압력 증가를 통해 환매로 인해 가격이 상승하기를 기대하면서 주식을 구매하고, 다음과 같은 경우 주식을 판매합니다. 거래 이벤트는 환매 완료를 확인합니다(더 많은 것을 원합니다!) **.**

**그럼 그렇게 해 보겠습니다. 의도 이벤트가 발생할 때마다 구매 통찰력** ( ) 을 생성 `InsightDirection.Up`하고 이를 반환할 통찰력 목록에 추가합니다.

```python
 # Iterate over transactions and parse information
for intention in intentions.Values:
    ## Generate Insights!
    # Skipping magnitude, confidence and source model and assigning 25% to weighting.
    insight = Insight.Price(intention.Symbol.Underlying, timedelta(days = 5), InsightDirection.Up, None, None, None, 0.25)
    insights.append(insight)
```

분석하려는 의도가 있는 주식 기호에 액세스하는 방법은 다음 `intention.Symbol.Underlying`과 같습니다. 인사이트에 5일의 유효 기간과 0.25의 가중치를 부여했습니다(역시 가중치가 항상 필요한 것은 아니지만, 우리가 사용할 포트폴리오 구성 모듈).

좀 더 정교하게 말하자면, 실제로 환매가 발생했을 때 그 날 해당 부동산을 사용하여 거래된 거래량의 5% 이상의 합리적인 거래량인 경우에만 재고에서 다시 매도할 것입니다 `transaction.VolumePercentage`.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_674+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/volume-percentage-1024x448.png)

해당 임계값에 도달하지 않으면 자사주 매입이 이벤트가 아닌 것으로 간주하고 일반적으로 추세를 보이는 기술 시장을 활용하기 위해 계속 보유할 것입니다.

```python
# Iterate over transactions and parse information
for transaction in transactions.Values:
    ## Generate Insights!
    # Skipping magnitude, confidence and source model and assigning 25% to weighting.
    if transaction.VolumePercentage != None and transaction.VolumePercentage > 5:
        insight = Insight.Price(transaction.Symbol.Underlying, timedelta(days = 5), InsightDirection.Down, None, None, None, 0.25)
        insights.append(insight)
```

이제 조정된 **SmartInsiderAlphaModel.py** 모듈은 다음과 같습니다.

```python
from QuantConnect.Data.Custom.SmartInsider import *
class SmartInsiderAlphaModel:
    
    def __init__(self):
        self.altDataSymbols = {}
    
    def Update(self, algorithm, data):
        insights = []
        
        ## Company buyback intentions and transaction data are provided
        ## by Smart Insider. A "buy-back" is when a company repurchases
        ## its own stock. It reduces the number of shares available to
        ## other investors, which in theory should reduce the supply of
        ## shares and increase the stock price.
        
        ## Smart Insider has two data sets available to use in your algorithm. 
        ## The Intentions data set is an announcement that establishes the intention
        ## to buy-back shares of the company. When the buy-back occurs this triggers
        ## a Transaction event with details about the execution of the buyback.
        ## Intention events always come before the Transaction event.
        
        # Fetch all transactions and intentions
        intentions = data.Get(SmartInsiderIntention)
        transactions = data.Get(SmartInsiderTransaction)
        
        # Iterate over transactions and parse information
        for intention in intentions.Values:
            ## Generate Insights!
            # Skipping magnitude, confidence and source model and assigning 25% to weighting.
            insight = Insight.Price(intention.Symbol.Underlying, timedelta(days = 5), InsightDirection.Up, None, None, None, 0.25)
            insights.append(insight)
                
        # Iterate over transactions and parse information
        for transaction in transactions.Values:
            ## Generate Insights!
            # Skipping magnitude, confidence and source model and assigning 25% to weighting.
            if transaction.VolumePercentage != None and transaction.VolumePercentage > 5:
                insight = Insight.Price(transaction.Symbol.Underlying, timedelta(days = 5), InsightDirection.Down, None, None, None, 0.25)
                insights.append(insight)


        return insights
        
    
    def OnSecuritiesChanged(self, algorithm, changes):
        ## Add SmartInsider Transaction and Intention data for each new equity
        for security in changes.AddedSecurities:
            if security.Type == SecurityType.Equity:
                transaction = algorithm.AddData(SmartInsiderTransaction, security.Symbol).Symbol
                intention = algorithm.AddData(SmartInsiderIntention, security.Symbol).Symbol
                self.altDataSymbols[security.Symbol] = (transaction, intention)

        ## Remove SmartInsider Transaction and Intention data for each new equity
        for security in changes.RemovedSecurities:
            if security.Type == SecurityType.Equity:
                algorithm.Liquidate(security.Symbol)
                transaction, intention = self.altDataSymbols.pop(security.Symbol, (None, None))
                algorithm.RemoveSecurity(transaction) if transaction is not None else None
                algorithm.RemoveSecurity(intention) if transaction is not None else None
```

### 3단계: QuantConnect의 포트폴리오 구성 예시 사용: Insight Weighted

이제 포트폴리오 구성 모듈을 선택해 보겠습니다.

다행히도 이들 모두는 내부적으로 모든 작업을 수행하며 수동 개입이 필요하지 않습니다. 그러나 이미 언급한 것처럼 일부 기능을 수행하려면 통찰력 개체에서 **통찰력 가중치를 내보내야 합니다.**

선택 사항은 다음과 같습니다.

- **동일 가중치** (가장 단순함)
- **Insight Weighted** (인사이트 가중치 필요)
- **섹터 균형**
- **블랙 리터맨**
- **평균-분산**

가장 마음에 드는 것을 선택하기 전에 [설명을](https://www.quantconnect.com/docs/algorithm-framework/portfolio-construction) 읽어보세요 !

예제를 계속하려면 Insight Weighted 모듈을 사용하겠습니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/insight-weighted-1024x561.png)

이는 단순히 설명에 따라 보유 크기를 결정하기 위해 할당한 **Insight Weight를 사용합니다.**

### 4단계: QuantConnect의 실행 엔진 예제 사용: 즉시

포트폴리오 구성과 마찬가지로 여기에서도 추가 작업이 거의 없습니다. 설명을 꼼꼼히 읽은 후 세 가지 선택 사항 중 하나를 선택하세요.

- **즉각적인**
- **표준 편차**
- **VWAP** (거래량 가중 평균 가격)

이것들은 모두 포트폴리오 구성 목표 목표를 달성하기 위해 거래를 하는 데 필요한 조건을 결정합니다.

예를 들어, 표준 편차 모듈은 평균 회귀를 활용하고 가격이 이동 평균의 X 표준 편차보다 낮을 때만 매수 주문을 합니다.

이는 추가 정보가 필요한 유일한 실행 모듈입니다. 이전 볼린저 밴드와 마찬가지로 되돌아보기 기간, 표준 편차 설정 및 데이터 해상도를 전달해야 합니다.

```python
self.SetExecution(StandardDeviationExecutionModel(60, 2, Resolution.Minute))
```

이 예에서는 간단하게 유지하고 즉시 실행을 진행하겠습니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/immediate-execution.png)

### 5단계: QuantConnect의 위험 관리 예시 사용: 포트폴리오 축소

마지막으로 위험 관리 모듈을 선택해 보겠습니다.

이것들은 모두 귀하의 포트폴리오(또는 포트폴리오의 일부)를 청산하기 위한 저조한 ​​성과 조건을 결정합니다.

선택 사항은 다음과 같습니다.

- **최대 미실현 이익**
- **트레일링 스톱 하락폭**
- **포트폴리오 축소**
- **부문 노출**
- **최대 감소**

다시 한 번 [설명을](https://www.quantconnect.com/docs/algorithm-framework/risk-management) 잘 읽어보세요.

이를 위해서는 조치를 취하기 전에 측정 기준에 따라 허용되는 최대 금액을 나타내는 생성자에 소수점을 전달해야 합니다.

예를 들어 포트폴리오 그리기 모듈을 사용해 보겠습니다.

```python
self.SetRiskManagement(MaximumDrawdownPercentPortfolio(0.03))
```

이는 최고점에서 최저점까지의 최대 포트폴리오 가치 손실이 3%를 초과하는 경우 포트폴리오를 청산합니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/risk-management.png)

## 우리의 두 번째 전략! Insider Insights를 사용한 기술주 백테스팅(SDF 백테스팅)

이제 SDF의 5개 구성 요소 모두에 대한 모듈을 선택하고 필요한 경우 수동 작업(예: Smart Insider 모듈에서 통찰력 생성)을 수행했으므로 백테스트를 위한 준비가 되었습니다!

이것이 우리의 최종 **main.py** 모습입니다.

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/sdf-demo-algo.png)

그 외에는 **SmartInsiderAlphaModel.py** 만 변경했습니다 . (전체 코드를 보려면 몇 섹션 위로 스크롤하세요).

드디어 백테스트 버튼을 누르자!

![](https://cdn.shortpixel.ai/spai/q_lossy+w_709+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/final-sdf-1.png)

그렇게 끔찍하지는 않습니다. 적어도 우리는 돈을 잃지 않았습니다!

하지만 그냥 매수해서 보유하는 것이 더 나았을 텐데…

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/benchmark.png)

실제 Insight를 확인해보세요!

![](https://cdn.shortpixel.ai/spai/q_lossy+w_730+to_webp+ret_img/algotrading101.com/learn/wp-content/uploads/2020/10/sdf-insights-2048x929.png)

## 마지막 생각들

여기까지 QuantConnect에 대한 기본 가이드입니다!

이 시점에서 QuantConnect의 가장 큰 단점은 배워야 할 내용의 양이 많다는 것이 자명할 것입니다.

이를 위한 문서는 합리적이지만 QuantConnect가 제공하는 예제 알고리즘이 때때로 불필요하게 복잡하고 설명이 형편없기 때문에 아직 능숙하지 않은 경우 내용이 어디서 나오는지 따라가기가 어렵다는 것을 개인적으로 발견했습니다.

또한 우리는 백테스팅 중에 우리가 찾을 수 없는 이유 때문에 때때로 인쇄되지 않는 버그와 같은 로그를 발견했습니다.

전반적으로, QuantConnect를 처음 사용하면 확실히 속도가 느려질 수 있습니다. 그러나 플랫폼은 매우 강력하며 많은 작업과 데이터 분석을 자동화하므로 장기적으로 학습할 가치가 있습니다!

마지막으로 Alpha Stream 생태계는 정말 흥미롭고 독특합니다.

## 코드 다운로드 링크

이 기사에 사용된 코드는  [여기에서](https://github.com/GregBland/QuantConnect_article) 찾을 수 있습니다 .