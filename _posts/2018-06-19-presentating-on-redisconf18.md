---
layout: post
title:  RedisConf18 발표 후기
date:   2018-06-19 21-00-00 +0900
comments: true
---
(개인적으로 중요한 마일스톤이었는데 기록이 없어서, 나중에 글을 추가했습니다.)

회사의 지원으로 샌프란시스코의 RedisConf18에 발표자로 참가해서, 발표를 하고 왔다. 15년 전쯤엔 모의토익에서 200~300점대였던 영어와 담 쌓았던 사람인데, 내가 영어로 발표를 하다니 감회가 새롭다.

LINE의 메시징 팀에서 Redis를 어떻게 사용하고 있는지에 대한 발표이다. LINE에서는 하루에 25 billion (250억건)의 메시지를 전송하고 있다. 이게 얼마만큼이냐면, message id가 32bits integer였으면, 매일매일 오버플로우가 난다. 매년 1월 1일의 경우는 새해 축하 메시지로 1초에 42만건을 전송하기도 했다. 메시징의 뒤에선 일반적인 RDBMS 대신 스토리지로서 Redis, HBase, Kafka 등등이 열일하고 있는데, Redis팀 입장에서의 발표라고 보면 된다.

내용에 사실 내 기여는 그리 많지 않고, LINE이 처음 생겼을때부터 여러 훌륭한 개발자들로부터 쌓여온 시스템들과, 최근에 추가된 것들, 내가 한 것 조금, 이런 것들이 섞여있는 것을 발표자료로서 정리하기만 한, 여러모로 얹혀가는 발표이다. 이거 내가 다 했어요 이런건 전혀 아니다. 80%정도가 포함된 비슷한 내용을 한국에서는 이미 다른 분이 몇 년 전에 했었다. 아무튼 우리 팀이 하고 있는 일에 대한 발표이긴 하다. (메시징 조직에서의 Redis팀이다.)

자세한 후기 기록은 회사 기술 블로그에 자세히 있어서 링크로 대체.

- 한글: [https://engineering.linecorp.com/ko/blog/presenting-on-redisconf18](https://engineering.linecorp.com/ko/blog/presenting-on-redisconf18)
- 일본어: [https://engineering.linecorp.com/ja/blog/presenting-on-redisconf18](https://engineering.linecorp.com/ja/blog/presenting-on-redisconf18)
- 영어: [https://engineering.linecorp.com/en/blog/presenting-on-redisconf18](https://engineering.linecorp.com/en/blog/presenting-on-redisconf18)

발표자료:

- [https://www.slideshare.net/slideshow/redisconf18-redis-at-line-25-billion-messages-per-day/99439316](https://www.slideshare.net/slideshow/redisconf18-redis-at-line-25-billion-messages-per-day/99439316)

발표영상:

- [https://www.youtube.com/watch?v=IxTUXuoIWro](https://www.youtube.com/watch?v=IxTUXuoIWro)