---
layout: post
title:  "GitHub 블로그란?"
date:   2021-10-10 10:00:00 +0200
categories: howto
---

## GitHub 블로그와 Jekyll

이 블로그는 `GitHub 블로그` 서비스를 통해 `호스팅`됩니다. `호스팅`은 서버나 웹페이지 등의 인터넷 서비스를 고객 대신 해주는 행위입니다. 호스팅 업체 덕분에 우리는 서버에 OS를 설치하거나, DB를 관리하거나, 네트워크 설정을 하는 등 복잡한 일에 신경을 쓸 필요가 없습니다.

GitHub 블로그는 내부적으로 `Jekyll`이라는 기술을 사용합니다. 이 기술은 `마크다운(markdown)` 문서를 HTML 웹문서로 변경해줍니다. 마크다운은 HTML에 비해 상당히 간소화된 문법을 가지고 있기 때문에, 포스팅 하나를 작성하는데 적은 시간과 노력이 필요합니다. 한편, 마크다운은 간단하지만 HTML은 강력합니다. 마크다운이 제공하지 않는 HTML의 기능을 사용하고 싶다면, 마크다운 문서 내에 HTML을 사용하면 됩니다. 파키우기 프로젝트에서는 이미지나 비디오 링크를 삽입하는 정도의, 간단한 HTML 기능을 사용할 것이라 예상합니다.

`Jekyll`로 만들어진 블로그는 `정적(static) 사이트`라고 합니다. 마크다운 문서(포스팅)를 포함한 블로그의 `소스 코드`가 Jekyll을 통해 웹페이지로 변환이 되면, 이 웹페이지는 우리에게 친숙한 방식으로 업데이트할 수 없습니다. 그래서 정적(static)이라고 하는 것이죠. 친숙한 방식(=동적, dynamic)이란, 마치 네이버 블로그나 티스토리, 워드프레스, 제로보드처럼 웹브라우저를 통해 편집을 하거나 새 글을 올릴 수 없다는 뜻이죠. 수정을 원한다면 `소스 코드`를 웹페이지로 변환하는 작업을 다시 해야 합니다. 다행히도 우리가 할 일은 수정하고 올리는 것 뿐입니다. 우리가 수정한 내용을 git을 사용해 GitHub에 올리기만 하면, GitHub이 자동으로 코드->웹페이지 변환 과정을 수행해주기 때문입니다.

`정적 사이트`의 단점은, 번번히 git을 통해 소스를 연동해야 하는 것이죠.
- 블로그 작업을 시작하려면 블로그의 소스코드를 GitHub에서 개인 컴퓨터로 내려받아야 합니다. 최초 한 번만 하면 되죠.
- 블로그를 수정하거나 새 글을 작성한 후에는 GitHub으로 올려야 합니다. 
- 다른 사람이 GitHub에 올린 새 내용은 내 개인 컴퓨터에 자동으로 반영되지 않습니다. 수동으로 연동해줘야 합니다. 습관을 들이면 되긴 합니다만...

반면에 장점 역시 명확합니다. `정적 사이트`는 자원을 적게 사용합니다. 그로 인한 부수 장점들도 존재하죠. 조금 설명을 해볼까요? 위에서 언급한 웹페이지들이나 웹서비스들, 즉 `동적 사이트`, 대부분은 데이터베이스가 필요합니다. 게시글은 데이터베이스에 저장되고, 우리가 웹페이지를 보려고 할 때마다 데이터베이스에 저장된 데이터를 웹페이지로 용환하는 연산작업이 필요합니다. 정리하자면, 정적 사이트에 비해 아래의 자원이 더 필요한 것입니다.
- 데이터베이스 실행에 필요한 자원
- 데이터베이스 데이터 저장공간에 필요한 자원
- 데이터베이스 데이터를 매번 웹페이지로 변한할 때 필요한 자원

반면에 정적 사이트는 소스 코드를 웹페이지로 변환하는 연산작업을 제외하고는 동적 사이트에 비해 압도적으로 적은 자원을 사용하죠. 이것 GitHub이 무료로, 광고도 없이, 블로그 서비스를 제공할 수 있는 이유 중 하나입니다. 물론 마케팅 관점의 이득도 있겠지만요. 다만, 환경의 관점에서 장점이라고 볼 수 있을지는 모르겠습니다. 내가 절약한 자원은 다른 이에게 점유당하는 것이, 이른바, 공유지의 운명일테니까요. 기타 장점으로는- 애초에 데이터베이스가 없고 민감한 정보를 저장하지도 않으니 보안의 우려가 적어집니다. 동적 사이트에 비해 연산이 적어지니 속도가 빠르기도 하죠.

간단한 개요를 마친 것 같습니다. 이제 소스코드를 어떻게 다루는지 알아볼까요?

## GitHub 소스코드 연동 with git

TODO 설명

#### Clone - 소스코드 내려받기

최초 한 번만 실행.

원하는 디렉토리에서 아래 명령어를 실행.

    $ cd ~/myworkspace # 원하는 디렉토리로 이동. 이름은 myworkspace가 아니라 무엇이든 상관없음.
    $ git clone https://github.com/pakiuki/pakiuki.github.io.git # 소스 내려받기
    Cloning into 'pakiuki.github.io'...
    remote: Enumerating objects: 31, done.
    remote: Counting objects: 100% (31/31), done.
    remote: Compressing objects: 100% (23/23), done.
    remote: Total 31 (delta 10), reused 27 (delta 6), pack-reused 0
    Receiving objects: 100% (31/31), 19.81 KiB | 1.17 MiB/s, done.
    Resolving deltas: 100% (10/10), done.
    $ cd pakiuki.github.io # 내려받은 소스가 있는 디렉토리로 이동
    $ ll # 파일 확인
    total 56
    drwxr-xr-x  12 j.oh.2  wheel   384 Oct 16 09:09 .
    drwxrwxrwt  25 root    wheel   800 Oct 16 09:12 ..
    drwxr-xr-x  12 j.oh.2  wheel   384 Oct 16 09:09 .git
    -rw-r--r--   1 j.oh.2  wheel    56 Oct 16 09:09 .gitignore
    -rw-r--r--   1 j.oh.2  wheel   419 Oct 16 09:09 404.html
    -rw-r--r--   1 j.oh.2  wheel  1125 Oct 16 09:09 Gemfile
    -rw-r--r--   1 j.oh.2  wheel  1874 Oct 16 09:09 Gemfile.lock
    -rw-r--r--   1 j.oh.2  wheel  2103 Oct 16 09:09 _config.yml
    drwxr-xr-x   5 j.oh.2  wheel   160 Oct 16 09:09 _posts
    -rw-r--r--   1 j.oh.2  wheel   539 Oct 16 09:09 about.markdown
    drwxr-xr-x   3 j.oh.2  wheel    96 Oct 16 09:09 asset
    -rw-r--r--   1 j.oh.2  wheel   175 Oct 16 09:09 index.markdown

#### Status - 수정한 파일 확인하기

새 파일을 추가하거나 수정하셨나요?

`git status` 명령어를 실행하면 어떤 파일을 고치고 수정했는지 알아볼 수 있습니다.

    $ git status
    On branch master
    Your branch is up to date with 'origin/master'.
    
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
    	modified:   _posts/2021-10-10-how-github-blog-works.md
    
    Untracked files:
      (use "git add <file>..." to include in what will be committed)
    	_posts/2021-10-16-my-new-post.md
    
    no changes added to commit (use "git add" and/or "git commit -a")

`2021-10-10-how-github-blog-works.md`를 수정하고 `2021-10-16-my-new-post.md`를 추가했다는 것을 알 수 있습니다.

#### Add & Commit - 수정사항 적용하기

#### Push - 수정사항 올리기

TODO

#### Pull  - 동료의 수정사항 내려받기

TODO

## Code에서 다운로드 받은 디렉토리를 열기

<p align="center">
  <img src="/asset/images/2021-10-10-code-open-folder.jpg" width="200px" />
</p>