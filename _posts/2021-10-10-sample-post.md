---
layout: post
title:  "샘플 포스팅"
date:   2021-10-10 12:55:00 +0200
categories: posts
description: 비워둬도 좋습니다. 혹시라도 검색최적화(SEO)를 원한다면 채워넣는게 좋습니다.
published: true
---

꼭 소스코드의 마크다운 파일을 확인해보세요.

---

# 제목 level1
## 제목 level2
### 제목 level3
#### 제목 level4
##### 제목 level5
###### 제목 level6

---

마크다운의 문법으로 소스코드에 포함된 이미지 삽입하기.

![파](/asset/images/pa.jpg)

위의 방식은 가운데 정렬이 안되는 문제가 있습니다. 이미지를 가운데에 표시하고 싶다면 HTML의 힘을 빌릴 수 있습니다.

HTML로 소스코드에 포함된 이미지 삽입하기.
<p align="center">
  <img src="/asset/images/pa.jpg" width="200px" />
</p>

HTML로 유튜브 영상 삽입하기.
<iframe width="560" height="315" src="https://www.youtube.com/embed/q_8wpvZmRhQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

외부 이미지 삽입하기. 이미지 파일을 제공하는 곳의 정책상, 잘 동작하지 않을 수 있습니다.
<p align="center">
 <img src="https://upload.wikimedia.org/wikipedia/commons/a/ab/Abraham_Lincoln_O-77_matte_collodion_print.jpg" width="100px" >
</p>

---

평범한 문장.

참고자료의 표시는 이렇게 [^1]

마크다운 파일의 다음 라인에 문장을 써도 같은 같은 줄에 표시됩니다. 다음 줄로 넘어가려면 줄의 마지막에 빈 칸 두 개를 추가해주세요.  
이렇게.  
또 이렇게.

문단과 문단 사이에는 추가의 빈 라인이 필요합니다. 그냥 줄넘김보다 간격이 더 넓죠?

볼드체 표현 **이렇게**.	이건 *이탤릭*. 물론 ***같이 쓸 수***도 있습니다.


> 사진과 인용이 있다고 해서 인터넷에서 읽은 모든 것은 그대로 믿지 말라. -아브라함 링컨
>> 이중 인용

---

`코드 넣기`. 개인적으로는 단어 강조할 때도 사용합니다.

한 문단의 앞 줄을 모두 스페이스 네 칸으로 띄워주면, 여러 줄의 코드블럭을 넣을 수 있습니다. 하물며 아래처럼 HTML도 그냥 쌩으로 보여줍니다.

    <html>
      <p>코드 보여주기</p>
    </html>

링크는 이렇게 표현할 수 있습니다. [구글로 바로가기](https://www.google.com/)

---

# References

[^1]: This is the footnote. [Google](https://www.google.com/)