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