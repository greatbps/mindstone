# Obsidian Jekyll 워크플로우

마지막 경향 8 월 15, 2021

> ## tl;dr
> 
> Obsidian Vault와 Jekyll 디렉토리를 동일하게 만듭니다. 메모의 파일 이름과 앞 문제 제목을 동일하게 만듭니다. Atom을 사용하여 Netlify를 피드하고 사이트를 제공하는 Github에 변경 사항을 푸시하십시오. 💥

[Obsidian은 내 작품을 만들고](https://refinedmind.co/obsidian-is-for-building-my-body-of-work)이 디지털 정원을 돌보는 것입니다. 내 워크 플로는 간단하지만 몇 가지 설정이 필요합니다. 이것이 우리가이 노트에서 다룰 내용입니다.

🌱 이 메모는 MacOS에서 자신의 정원과 간단한 워크 플로를 설정하려는 동료 디지털 정원사를 돕기위한 것입니다. 이것은 분명히 내가 작성한 최초의 "기술 연습"이므로 아래에 의견을 말하거나 [트위터에](https://twitter.com/miketnnnbm) 문제, 도전 또는 혼란이 있음을 알리**십시오**. 누리다!

---

본질적으로, 내 워크 플로는

```
Obsidian → Atom → Github → Netlify → https://refinedmind.co
```

## 내 설정으로 다이빙

이 사이트는 다음에서 실행 중입니다.

-   [지킬](https://jekyllrb.com/)
-   [넷리파이](https://www.netlify.com/)
-   [깃허브](https://www.github.com/)

이 단어들은 [옵시디언](https://obsidian.md/)으로 쓰여져 있습니다.

백엔드는 [Atom 텍스트 편집기](https://atom.io/)에서 관리됩니다.

그러나 Obsidian에 도착하기 전에 모든 것이 [내 디지털 생태계](https://refinedmind.co/my-digital-ecosystem)의 어딘가에서 시작됩니다. [아이디어는 그들에 대해 생각하지 않고 그들에 대해 글을 쓰면서](https://refinedmind.co/ideas-improve-by-writing-about-them-not-by-thinking-about-them) 개선되며,이 사이트의 모든 목적 인 아이디어 개선.

평생 인터넷에서 물건을 쌓아 왔지만 나는 타입의 사람이 아니기 때문에 지킬 기반 디지털 원예 템플릿을 맑은 연습으로 은혜롭게 공유 한 Maxime Vaillancourt가 만든 기초 위에 세웠습니다.`code from stratch`

## Max의 디지털 정원 템플릿을 Mac에서 실행되는 Obsidian 볼트와 연결하는 방법은 다음과 같습니다.

### 1. 도구 및 백엔드 시스템 설치

1.  [Atom 텍스트 편집기 다운로드](https://atom.io/)
2.  [Max의 디지털 정원 설정을 살펴보십시오](https://maximevaillancourt.com/blog/setting-up-your-own-digital-garden-with-jekyll) _(시간이 걸리므로 편안하게하고 일이 작동 할 때 여기로 돌아 오십시오)_
3.  [최신 버전의 옵시디안 설치](https://obsidian.md/)
4.  Obsidian에서 새 Vault를 만들고 위치를 기본 Jekyll 디렉토리 내의 디렉토리로 설정하십시오.`_notes`
5.  안에 새 디렉토리를 만들고 이름을 지정하십시오. `_notes``_staging`

> ✅ 이 시점에서 당신은 당신의 지킬 설치와 동일한 디렉토리 내에 작동하는 지킬 설치 (감사합니다 맥스!) 및 옵시디언 볼트 설정이 있어야합니다.

---

### 2. 두 개의 노트 만들기 및 연결

Jekyll은 내에서 마크 다운 파일을 가져 와서 정적 페이지로 변환하여 작동합니다. 디렉토리에 넣었 기 때문에 Gibhub 리포지토리는 폴더를 동기화하지만 Jekyll의 기능을 방해하지는 않습니다. 이 폴더는 작업 중인 메모에 사용할 수 있지만 공개 정원에서 라이브로 이동할 준비가 되지 않았습니다.`_notes``_staging``_notes`

#### 첫 번째 메모 작성

1.  Obsidian 창을 열고 왼쪽 사이드 바 내의 폴더를 마우스 오른쪽 버튼으로 클릭하고 새 메모를 작성하십시오.`_notes`
2.  제목을 지정하고 공백을 포함하십시오. 지킬은 그들을 잘 처리 할 것입니다.`my new digital garden`
3.  지킬 "앞 문제"를 복사하여 메모 상단에 붙여 넣으십시오. 사이트에 표시하려는 모든 메모에 추가해야합니다.
    
    ```
    --- title: ---
    ```
    
4.  _내 새로운 디지털 정원_이라는 단어를 추가하여 읽습니다. `title:`
    
    ```
    --- title: my new digital garden ---
    ```
    

이제 마크 다운 파일 ()의 제목은 Jekyll이 파싱 할 메모의 제목과 일치합니다 (). 이것은 Github에 모든 것을 푸시 할 때 모든 링크와 백 링크가 서로 연결되는 방법입니다.`my new digital garden.md``title: my new digital garden`

> ❗️ 메모가 있다는 것을 알았을 때 링크가 작동하지 않는 경우 마크 다운 파일의 제목이 앞 문제의 제목과 정확히 일치하는지 확인하십시오.

#### 몇 가지 콘텐츠를 추가해 보겠습니다.

앞면 문제 아래에서 다음을 복사하여 메모 본문에 붙여 넣으십시오.

```
Welcome to my garden! This is where I explore my ideas and share them publicly so others can read and provide feedback to help me improve my thinking.
```

#### 새 메모에 연결

텍스트를 선택하고 선택 영역을 대괄호로 자동 감싸는 이중 대괄호를 입력합니다. 이것이 새로운 노트에 연결하는 한 가지 방법입니다.`improve my thinking``[[`

COMMAND를 누른 상태에서 새로 생성 된 링크를 클릭하여 자동으로 제목이 지정된 빈 메모가 포함 된 새 창을 엽니 다.`improve my thinking`

다시 한 번 앞 부분을 복사하여 메모 맨 위에 붙여 넣으십시오.

```
--- title: ---
```

> 🚨 자, 이것은 중요합니다 : 메모의 제목이 앞 문제의 제목**과 정확히 일치하는지** 확인하십시오. 그렇지 않으면 Jekyll 내에서 상황이 제대로 연결되지 않습니다.

이 새로운 메모에 대한 귀하의 주요 문제는 다음과 같아야합니다.

```
--- title: improve my thinking ---
```

#### 새 메모 작성

그 메모에 몇 문장을 쓰는 재미를 느끼고 계속 진행합시다.

---

### 3. 설치 아톰 편집기

1.  아톰 텍스트 편집기 열기
2.  파일 > 프로젝트 폴더 추가를 클릭합니다.
3.  Jekyll 설치의 기본 디렉토리를 선택하십시오. Max의 연습을 따랐다면 이 디렉토리가 됩니다. 이제 모든 지킬 파일과 아톰 에디터 내에서 볼 수 있습니다.`my-digital-garden``_notes`
4.  오른쪽 창 창에서 단추를 클릭하고 프롬프트에 따라 기본 프로젝트 폴더 내에 git 저장소를 설정하십시오.`Create repository`

이제 _준비되지 않은 변경 내용이_ 있는 파일 목록이 표시됩니다. 를 클릭하고 해당 변경 내용이 _단계적 변경 내용_ 섹션으로 이동하는 것을 확인합니다.`Stage All`

---

### 4. Github에 변경 사항 푸시

1.  텍스트 상자에 짧은 메모를 입력합니다. `Commit message`
    
    ```
    Just setting up my dgtl grdn
    ```
    
2.  클릭 `Commit to master`
3.  편집기의 상태 표시 줄의 맨 아래에서 Github에 변경 사항을 푸시하려면 클릭하십시오.`⇧Push 1`

> 💾 파일이 인터웹으로 꺼져 있습니다!

여기에서 Github이 변경 사항을 인식하고 Netlify가 사이트에 배포하는 데 몇 분 정도 걸립니다.

Once that’s done, your digital garden should be available on the Internet via a generic Netlify URL, which you can change to a custom domain later if you’d like.

![](https://s2.googleusercontent.com/s2/favicons?domain_url=https://maximevaillancourt.com/blog/setting-up-your-own-digital-garden-with-jekyll&sz=64)

Setting up your own digital garden with Jekyll

[Go to text →](https://maximevaillancourt.com/blog/setting-up-your-own-digital-garden-with-jekyll)

---

## 모두 완료! 정원을 즐기십시오!

### 마무리하기 위해 정원을 돌보는 작업 과정은 다음과 같습니다.

> 1.  Obsidian에서 노트 쓰기, 편집 및 링크
> 2.  Atom을 통해 Github에 변경 사항을 커밋하고 푸시하십시오.
> 3.  그거에요! Github + Netlify가 자신의 일을 할 때까지 기다리면 정원이 몇 분 안에 업데이트됩니다!

---

이 연습과 함께 따라 주셔서 감사합니다! 나는 그것이 당신에게 도움이되고 가치 있었고, 전혀 혼란스럽지 않기를 바랍니다.

즐거운 정원 가꾸기!

🌱

_내 작품이 어떤 식 으로든 도움이된다면 [커피☕를 사주는 것을 고려하십시오!](https://www.buymeacoffee.com/miketannenbaum)_