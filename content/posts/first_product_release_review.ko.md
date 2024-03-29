---
title: "처음으로 프로덕트를 공개해본 후기"
date: 2023-11-16T01:30:12+09:00
summary: "AI 퀴즈 노트앱을 공개하고 망해본 후기"
tags: ["Reflex", "Python", "AWS", "Product"]
---
# 계기

저는 Notion을 공부에도, 개인적인 서류 정리 작성 및 정리에도 요긴하고 활용하고 있습니다. 평소처럼 전공 과목 퀴즈를 맞아 평소 강의를 들으며 작성해두었던 페이지를 들으며 공부하고 있었습니다. 내가 정말 외우고 있는지 백지에 써보면서 검증하고 있는데, 문득 연습문제가 있었으면 좋겠다는 생각이 들었습니다.

# 프로덕트 구성하기

창업 관련 교육에서 강조하는 것 중 하나는 개념 증명(PoC)는 누구나 할 수 있다는 것입니다. 실물 앱 없이 단순한 포스터 하나, 아니면 피그마 프로젝트 하나 그것도 없다면 설문이나 인터뷰만으로도 가능하다는 것이죠. 오히려 개발 함정에 빠질 수 있기 때문에 충분한 개발 능력이 있더라도 프로토타입 앱 개발은 악수일 수 있습니다. 하지만 저는 개발자이기 때문에 빠르게 개발해서 데모를 공개하기로 했습니다.

## 구성

AWS EC2 서버와 S3 + CloudFront CDN으로 배포했습니다. 최소로 개발하기 위해서 데이터베이스나 외부 저장은 전부 제외했고, 로깅 또한 별개의 시스템 없이 파일에 단순 쓰기 방식으로 만들었습니다. 

{{< figure src="/static/images/egonote-note-page.png#center" alt="Note 작성 페이지의 모습" width="40%" >}}
{{< figure src="/static/images/egonote-quiz-page.png#center" alt="Quiz 페이지의 모습" width="40%" >}}

# 공개

첫 공개 대상은 제 친구들입니다. 제 프로덕트를 아주 대차게 까줄(…) 준비가 되어 있었기 때문에 첫 타겟으로 했습니다. 예상대로 극렬한 비판을 맛볼 수 있었습니다. 

## 단점

1. 사용법 직관성이 떨어진다.
    1. 특히 대차게 까였습니다.
    2. 설명이 부족하다.
    3. 노트 작성할 자리에 설명이 있어서, 한 번 쓰면 알 방법이 없다.
    4. 최소/최대 크기 제한 고지가 없다.
2. 생성 속도가 너무 느린데, 이에 대한 고지가 없다.
3. 다른 사람들한테 공유 못해주겠다. 그냥 개구리다…

## 장점

1. 아이디어 자체는 나름 유용한 것 같다
2. 정말 괜찮게 나온다면 써볼 의향이 있긴 하다

# 후기

처참한 결과를 예상하긴 했지만… 예상보다도 처참했습니다. 예상과 가장 달랐던 것은 UI/UX 부분이었습니다. 이번에 가장 검증하고 싶었던 것은 `AI가 자신의 자료로 만들어주는 연습문제 시스템을 사용할 의사가 있나`였습니다. 사용할 의사가 없지는 않다는 것을 확인하기는 했습니다. 다만 친구라서 제가 한 부가적인 보충 설명까지 다 들은 후에야 확인할 수 있었습니다. 친구가 아니었다면 다 들어보기도 전에 그냥 넘겨버렸을 겁니다. 공개된 프로덕트의 UI/UX가 정말 검증하려고 싶었던 아이디어 검증을 방해하는 셈이죠.

이전에 아이디어 검증에 관해서 배우길 개발 전혀 할 필요 없다고 했던 것이 기억납니다. 오히려 안 하는 것이 더 좋다고도 했었죠. 그럼에도 불구하고 개발자라는 아이덴티티를 가지고 있는지라 그래도 개발한 것으로 검증해보고 싶다는 마음에 개발한 것으로 검증했었습니다. 아이디어 검증이 왜 단순한 게 좋은지 깨닫게 된 좋은 계기였습니다. 앞으로는 사이드 프로젝트를 할 때 노 코드 웹페이지 툴을 사용해보는 것을 고려할 것 같습니다. 물론 백엔드는 직접 할 생각입니다.
