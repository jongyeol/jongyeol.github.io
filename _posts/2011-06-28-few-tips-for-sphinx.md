---
layout: post
title:  Sphinx 사소한 팁 몇가지
date:   2011-06-28 19-52-00 +0900
---
요 몇일간, 모 사이트에 Full-Text 검색을 붙이려고 [Sphinx][sphinx]를 만지며 놀았다. 처음엔 [Lucene][lucene]을 고려했으나, 해당 사이트의 서버사이드는 Java 기반이 아닌 PHP였고, 내 서버도 아닌데 단지 검색 때문에 JVM을 띄우는 것은 왠지 죄책감이 느껴졌다. 결정적으로, Sphinx를 붙이는 것은 Lucene을 붙이는 것 보단, 훨씬 손이 덜 갈 것으로 판단했다.

Sphinx를 처음 써보거나, 도입을 고려하는 사람을 위해서 몇 가지 말을 해보자면,

1. Lucene을 적용하는 것 보단 훨씬 간단하다. 특히, PHP, Ruby, Python의 경우 좋을듯.
1. 백엔드가 DB인 경우(특히 MySQL)에도 매우 간단하다. 코드 한 줄 필요 없고 최소한의 설정으로 바로 인덱싱 및 검색이 가능하다.
1. 백엔드가 DB가 아닌 경우는 [xmlpipe2 driver][xmlpipe2]만 만들어주면 된다.
1. Lucene처럼 동작을 어느정도 이해할 필요가 전혀 없다.
1. 한글 및 [CJK][cjk] 검색은 기본적으론 되진 않지만, [CJK ngram characters][cjk-ngrams]를 설정하면 된다.
1. CJK 경우는 형태소 분석기가 내장되어 있지 않다.
1. ngram의 길이는 옵션으로 줄 수 있지만, 1 밖에 안 된다. 2 이상이면 assert 에서 죽는다고 한다. -_-;;
1. ngram으로 하면, 한글이 한 글자씩 분리되서 검색이 된다. "종텐"을 검색하는 경우에, "텐종"은 물론, "종어쩌구저쩌구텐"이라던가, "텐어쩌구 저쩌구 종"도 검색된다. -_-;; 문서의 길이가 긴 경우에는, 한글 형태소 분석기를 구현하거나, Lucene에 CJK 형태소 분석기를 달아서 쓰는 편이 나을 수 있다.
1. 0.9.9 가 마지막 stable release 이지만, 없는 기능도 좀 있고, 버그도 있으니깐, 최신 버전을 빌드해서 쓰는걸 권장한다.
1. field 내용이 결과에 포함되지 않는 점이 xmlpipe2로 사용하는 경우는 꽤 불편한데, 1.10-beta 이상부턴 이를 지원한다.
1. 1.10-beta는 SetLimits 함수에 심각한 버그가 있다. 2.0.1-beta 이상을 빌드해서 사용할 것.
1. document id 를 64비트 정수로 하려면, ./configure --enable-id64 로 빌드해야 한다. 실행했을 때에 id64가 써있으면 64비트로 빌드된 것이고, 그렇지 않다면 64비트 시스템이라 하더라도 32비트로 빌드된 것이다.
1. 언어에 상관 없이, [PHP로 커스텀 검색 엔진 구현하기 (한글)][php-sphinxsearch]를 한번 읽어보면 좋다.

-- 이상한 나라의 종텐.

[sphinx]: http://sphinxsearch.com/
[lucene]: http://lucene.apache.org/
[xmlpipe2]: http://sphinxsearch.com/docs/2.0.1/xmlpipe2.html
[php-sphinxsearch]: http://www.ibm.com/developerworks/kr/library/os-php-sphinxsearch/
[cjk]: http://ko.wikipedia.org/wiki/CJK
[cjk-ngrams]: http://sphinxsearch.com/wiki/doku.php?id=charset_tables#cjk_ngram_characters
