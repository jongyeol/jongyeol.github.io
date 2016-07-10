---
layout: post
title:  Ctags, Cscope for Android
date:   2011-12-03 23-19-00 +0900
---
오늘, [Google Developer Hackaton Korea][gdhk]에 참여하면서, 안드로이드 태블릿을 위한 코드뷰어를 만들기 위해서, ctags와 cscope를 Android NDK에서 빌드되게끔 포팅했다. 코드뷰어는 다 못만들어서 틈틈히 만들 예정이고, 포팅한 ctags와 cscope를 github에 올렸다.

* [Ctags for Android][ctags-android]
* [Cscope for Android][cscope-android]

Ctags는 원래 GPLv2 라서, GPLv2로 할 수 밖에 없었고.. Cscope는 원래는 BSD였는데 포팅하면서 필요한 몇몇 파일을 glibc에서 가져왔더니 GPLv2 가 되어버렸다. 아놔. 결국 둘 다 내가 싫어하는 라이센스 GPLv2가 되었다. 안드로이드에서 ctags, cscope 같은 파일을 직접 실행할 일은 거의 없으나, 뭐 올려두면 누군가는 도움이 될까 싶어서 올린다. Cscope같은 경우는 ncurses를 포팅할 수가 없어서, ncurses를 사용하는 부분은 동작하지 않게 했다. 즉, 인덱스 생성 등도 되고, 커맨드라인에서 옵션으로 검색하는 것도 정상적으로 되지만, ncurses가 필요한 GUI틱한 화면은 동작하지 않는다.

참고로, 루팅한 폰/태블릿에서는 adb shell 연결하고 chmod로 실행권한만 주면, adb shell에서 바로 실행해볼 수 있고, 루팅하지 않은 폰/태블릿에서는 /data/data/자기앱/ 안에 복사하고 권한조정을 해야 한다. 근데, <strike>오늘 해커톤에서 해본바로는 Java의 File.setExecutable 로는 권한이 변경되지 않고, 뭔가 다른 방법을 해보려다가 시간이 다 되서 망했다.</strike> 나중에 해보니 잘 된다. File.setExecutable 문제가 아니었다.

-- 이상한 나라의 종텐.

[gdhk]: https://plus.google.com/s/%23gdhk
[ctags-android]: http://github.com/jong10/ctags-android
[cscope-android]: http://github.com/jong10/cscope-android
