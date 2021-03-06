# 10 주차 주간회고

## 🎉 한 것

- 개인 프로젝트 진행

https://codesoom.github.io/project-react-2-gringrape/

### CI/CD, 리팩토링

1주차때 빠르게 사용할 수 있는걸 만들려고 달렸던 탓에, 코드가 이상한 부분이 많았다. 인수테스트도 없었고, CI 도 돌지 않았다. 수형님이 2주차 초반에 CI에 대해 조언해 주셔서 CI 와 CD 를 설정하는 작업을 가장 먼저 진행했다. 온갖 삽질 끝에 적용하고 나서 엉망인 코드를 손보기 시작했다. 얼마안걸릴줄 알았는데, 코드 작성한 시간보다 리팩토링한 시간이 많았던것 같다. 역시 만들면서 리팩토링 단계를 잘 안하면 다 갚게 되어있다..

### 피드백 반영

공개하고 나서도 생각보다 사용자 피드백이 오지 않았다. ㅜ 카페 분위기가 온화해서 냉정한 피드백이 안달리는 것 같다. 리팩토링하면서 중간에 윤석님이 피드백을 주셔서 해당 부분을 손보았다. 작은 부분이라고 생각했지만, 하나하나가 반영하기 매우 어려웠다. 사용자가 마이크 입력 중일때, 마이크 색깔을 바꾸는 것은 꼬박 하루가 넘게 걸렸다. 밥먹다가도 고민하고 낮잠자다가도 고민하고 장보러가서도 고민하고 아무리 고민하고 코딩해도 어떻게 하는지 답이 안보였다. 그러다가 함수형 자바스크립트 스터디를 하게되었는데 거기서 리액티브 프로그래밍이란 단어를 훑어가면서 보게 되었다. 마이크 입력에 반응하는 거니 리액티브 아닌가 ㅋㅋ 라는 매우 단순한 생각으로 이것저것 알아보고 예제를 만들었는데, 적용에 성공해서 기분이 너무 좋았다. 

### 자문 해주실 분이 나타났다

카페에서 유의미한 피드백은 별로 못얻었지만, 내용을 좋게봐주신 현직 언어치료사 분께서 따로 연락을 해오셔서 기능에 대해 지속적으로 피드백을 주고 싶다고 하셨다. 나는 한가지 케이스 밖에 사례를 모르기 때문에, 내가 구상한 것들이 유용할까 의구심이 많던 차에 굉장히 감사했다. 주소를 알려드리니 바로 깃헙에 가입하셔서 구상한 것들에 대한 피드백을 해주셨다. 

## 📗 배운것, 느낀것

### Reactive Programming

배웠다기 보다 맛을 보았다. Observable 을 사용해서 비동기고 동기고 복수고 단수고 일관되게 스트림으로 처리해 버리니 매우 강력하다는 것을 느꼈다. 나는 간단하게 음성인식 모듈에서 이벤트 스트림을 Observable 로 건네주어 , thunk 에서 구독하고 액션을 적용하는 것만 구현했다. 비동기 문법이 전혀 필요없이 테스트까지 완전 쉬워져서 상당히 좋았다. 

어려워보이는게 나오면 굳이 지금 배워서 적용해야 하나라는 생각을 많이 가지고 살았는데, 이번 계기로 생각이 완전히 바뀌었다. 뭔가 느낌이 온다 싶으면 예제라도 무조건 만들어보고 이런거구나 라는 느낌만 생겨도 문제를 해결할때 생각나는 가짓수가 훨씬 풍성해질 것 같다.

그 이후에 thunk 에서 dispatch 를 계속 달고 다니고 스토어를 모킹하는게 마음에 들지 않아서, 찾아보니 테스트가 쉬워진다고 redux-saga 와 redux-observable 을 보게 되었다. (쉬워지지 않았다...) redux-saga 부터 적용해보려고 예제를 몇번이고 쳐보면서 익숙해지고 개념도 계속 읽어본후에 적용해봤다. 뭔가 잘되는것 같았으나 작성해놓은 RxJS 로직과 합칠 수가 없어서 포기했다. redux-observable 로 타겟을 바꾸고 열심히 공부해서 적용해보았다. 공식문서에는 마블링 테스트인지 뭔지 괴물같은 테스트 방법이 나와있었지만, 너무 어려워 보여서 전통적인 테스트방법을 택했다. 하루 종일 씨름하다가 적용해 성공했다.

코드는 단순해지기보다 복잡해졌지만, 개념적으로 다 스트림이라서 결론적으로는 심플해져서 좋다. 시작이 반이라는 생각으로 좀 더 지식을 확장해가면서 단순하게 만들고, 그래도 복잡하면 일부분은 thunk 를 쓰는 것도 고려해보아야 겠다. 

## 🎈 할 것

써놓고 보니 뭘 구현한게 별로 없는 한주 였던것 같다.... 남은 2주 마지막 마무리를 잘 짓기 위해서 자문해주신 기능도 추가하고 디자인도 손봐서 코드숨을 잘마쳐야겠다. 운영은 계속해서 해야겠지만, 이왕 기한을 잡고 시작한 일일 만큼 기한내에 잘 마무리 짓고 싶다. 매일 같이 할 수 있을까 의구심이 들지만, 주어진 하루에 최선을 다해야 겠다. 
