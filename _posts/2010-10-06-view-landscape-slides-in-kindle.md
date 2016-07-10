---
layout: post
title:  킨들에서 가로로 된 강의자료 보기
date:   2010-10-06 14-10-00 +0900
---
킨들(3세대)에서 가로로 된 강의자료(pdf)를 보려면, 꽤 만족스럽지 않다. 몇가지 문제가 있는데,&nbsp;킨들 안에서 가로로 회전을 하면 A4 용지랑 킨들의 화면 비율이 달라서, PDF에서의 한 페이지가 킨들의 화면을 조금 넘어간다. 그래서, 한 페이지의 90% 정도가 첫 페이지에 나오고, 두번째 페이지엔 10% 정도만 나온다. -_-;; 킨들에는 fit-to-screen 으로 비율을 조정하는 방법이 있는데, 이 옵션은 **가로에 맞춰져서 나오지, 세로에 맞워져서 나오진 않는다.**

뭔가 방법이 없을까 하다가, 다양한 PDF 생성기를 설치해보고, 별 짓을 다 해봤으나, (1) 한글이 안되거나, (2) 해당 프로그램으로 PDF를 회전 하면 그림이나 그래프가 깨지거나, (3) 페이지가 결국 넘어가거나.. 으악! 킨들 실망이야! 라고 생각하다가, Python 으로 간단히 반시계로 회전하는 코드를 짰다. 그래프나 그림, 한글도 안 깨진다. 아래 주소에 코드를 올려놨다.

* Rotate a pdf to landscape for Kindle : http://gist.github.com/612853

회전된 상태인데도, 글자 검색도 잘 된다. 아 이제, 강의자료를 킨들에 다 넣을 수 있으니.. 공부만 하면 되는건가?...

-- 이상한 나라의 종텐.