# Node.js
***
참고서적: Node.js 교과서 by 조현영   
참고강의: [인프런강의](https://www.inflearn.com/course/node-js-%EA%B5%90%EA%B3%BC%EC%84%9C#)   

## 1. 노드 시작하기   
* 노드란?   
Node.js는 Chrome V8 JavaScript엔진으로 빌드된 JavaScript런타임입니다.   
Node.js는 **이벤트 기반, 논 블로킹 I/O 모델**을 사용해 가볍고 효율적입니다. **(+싱글 스레드)**   
Node.js의 패키지 생태계인 npm은 세계에서 가장 큰 오픈소스 라이브러리 생태계이기도 합니다.   

## 2. 알아두어야 할 자바스크립트
* **var** vs **const** vs **let**   
**var**은 함수 스코프를 가지므로 블록 밖에서도 변수를 사용할 수 있다. 반면, const와 let은 블록 스코프를 가지므로 블록 밖에서는 변수에 접근할 수 없다.   
**const**는 한 번 대입하면 다른 값을 대입할 수 없다. 또한, 초기화 시 값을 대입하지 않으면 에러가 발생한다. **let**은 값을 변경할 수 있다.   
따라서 기본적으로 변수 선언 시에는 const를 사용하고, 다른 값을 대입해야 하는 상황이 생겼을 때 let을 사용한다.   

* 템플릿 문자열   
문자열 안에 변수를 사용하고 싶을 때 따옴표 대신 백틱으로 감싸 '${변수}입니다'와 같이 사용 가능.   

* 객체 리터럴의 변화
<pre>
var sayNode = function() {
    console.log('Node');
};
var es = 'ES';

// 이전 문법
var oldObject = {
    sayJS: function() {
        console.log('JS');
    },
    sayNode: sayNode
};
oldObject[es + 6] = 'Fantastic';

// 추가된 문법
const newObject = {
    sayJS() { // 1. 객체 내 메서드를 선언할 때 콜론(:)과 function 생략 가능
        console.log('JS');
    },
    sayNode, // 2. 속성명과 변수명이 겹치는 경우 한 번만 작성 가능
    [es + 6]: 'Fantastic' // 3. 객체의 속성명을 동적으로 생성 가능
};
</pre>

* 화살표 함수
<pre>
function add(x, y) {
    return x + y;
}
const add = (x,y) => x+y; // function 대신 => 사용, return 생략 가능
</pre>
