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

### 2. Create and link two notes

Jekyll works by taking any markdown file within and turning it into a static page. Since you’ve put within the directory, your Gibhub repo will sync the folder but it will not interfere with the functionality of Jekyll. You can use this folder for notes you’re working on but are not ready to go live on your public garden.`_notes``_staging``_notes`

#### Make your first note

1.  Open your Obsidian window, right click on the folder within the left sidebar, and make a new note.`_notes`
2.  Give it the title and include the spaces. Jekyll will process them just fine.`my new digital garden`
3.  Copy and paste the Jekyll “front matter” to the top of the note. You’ll have to add this to every note you want to appear on your site.
    
    ```
    --- title: ---
    ```
    
4.  Add the words _my new digital garden_ to so it reads `title:`
    
    ```
    --- title: my new digital garden ---
    ```
    

Now the title of the markdown file () matches the title of the note Jekyll will parse (). This is how all your links and backlinks will connect to one another when you push everything to Github.`my new digital garden.md``title: my new digital garden`

> ❗️ If you find links not working when you know the notes exist, make sure the title of the markdown file matches the title within the front matter exactly.

#### Let’s add some content

Below the front matter copy and paste the following into the body of the note:

```
Welcome to my garden! This is where I explore my ideas and share them publicly so others can read and provide feedback to help me improve my thinking.
```

#### Link to a new note

Select the text and type double brackets which will automatically wrap that selection in brackets. That’s one way to link to new notes.`improve my thinking``[[`

While holding COMMAND, click on that newly created link to open a new window containing a blank note that’s automatically been titled .`improve my thinking`

Once again copy and paste the front matter to the top of the note:

```
--- title: ---
```

> 🚨 Now, this is important: make sure the title of the note **matches exactly** to the title in the front matter. If it doesn’t, things will not link properly within Jekyll.

Your front matter on this new note should look like this:

```
--- title: improve my thinking ---
```

#### Write your new note

Have some fun writing a few sentences in that note and let’s move on.

---

### 3. Setup Atom editor

1.  Open Atom text editor
2.  Click File > Add Project Folder
3.  Select the main directory of your Jekyll installation. If you followed Max’s walkthrough, this will be the directory. You should now see all your Jekyll files and within the Atom editor.`my-digital-garden``_notes`
4.  In the right window pane click the button and follow the prompts to setup a git repository within the main project folder`Create repository`

You should now see a list of the files with _Unstaged Changes_. Click and watch them move down to the _Staged Changes_ section.`Stage All`

---

### 4. Push changes to Github

1.  Enter a short note in the text box for `Commit message`
    
    ```
    Just setting up my dgtl grdn
    ```
    
2.  Click `Commit to master`
3.  At the very bottom in the status bar of the editor, click to push the changes to Github`⇧Push 1`

> 💾 Your files are off to the interwebs!

From here it will take a few minutes for Github to recognize the changes and Netlify to deploy them to your site.

Once that’s done, your digital garden should be available on the Internet via a generic Netlify URL, which you can change to a custom domain later if you’d like.

![](https://s2.googleusercontent.com/s2/favicons?domain_url=https://maximevaillancourt.com/blog/setting-up-your-own-digital-garden-with-jekyll&sz=64)

Setting up your own digital garden with Jekyll

[Go to text →](https://maximevaillancourt.com/blog/setting-up-your-own-digital-garden-with-jekyll)

---

## All done! Enjoy your garden!

### To wrap up, your workflow for tending your garden is as follows:

> 1.  Obsidian에서 노트 쓰기, 편집 및 링크
> 2.  Atom을 통해 Github에 변경 사항을 커밋하고 푸시하십시오.
> 3.  그거에요! Github + Netlify가 자신의 일을 할 때까지 기다리면 정원이 몇 분 안에 업데이트됩니다!

---

이 연습과 함께 따라 주셔서 감사합니다! 나는 그것이 당신에게 도움이되고 가치 있었고, 전혀 혼란스럽지 않기를 바랍니다.

즐거운 정원 가꾸기!

🌱

_내 작품이 어떤 식 으로든 도움이된다면 [커피☕를 사주는 것을 고려하십시오!](https://www.buymeacoffee.com/miketannenbaum)_