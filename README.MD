# JS_CH4
4 - 1 : 콜백 함수 예제(1-1) setInterval
    콜백함수 제어권에 관련된 예제이다. setInterval에 첫번째 인자로 무기명함수를 넘겨주었다. 0.3초마다 timer실행 count가 4를 넘기면 clearInterval 호출 및 종료

4 - 2 : 콜백 함수 예제(1-2) setInterval
    4 - 1의 예제코드를 보기쉽게 변경하였고 동작원리는 같다.

4 - 3 : 콜백 함수 예제(2-1) Array.prototype.map
    newArr를 변수로서 선언 후 map함수를 할당하였고 인자로 함수를 넘겨주었다. 넘겨받은 인자는 currentValue, index를 인자로 갖는다. map 함수는 Array.prototype의 메서드로써 기본으로 받는 인자는 currnetValue, index, array를 받지만 본 코드에서는 마지막 array를 생략하였다. 

4 - 4 : 콜백 함수 예제(2-2) Array.prototype.map - 인자의 순서를 임의로 바꾸어 사용한 경우
    임자의 순서를 임의로 바꾸어 사용할 수 없다. 본 코드에서 map의 인자로 받는 currentValue와 index의 순서를 바꾸었다. 하지만 이는 이름만 바뀐 것이고 map이 받는 인자순서는 변경되지 않기 때문에 결과값은 4 - 3과 달라진다. 

4 - 5 : 콜백 함수 예제(2-3) Array.prototype.map - 구현
    4 - 3, 4 - 4에서 쓰인 Array.prototype.map 함수를 직접 구현한 예제이다. currentValue, index, array를 위 코드에선 각 인자의 형태를 this[i], i, this로 받아 쓰고 있다. this에 다른 값이 담기는 이유는 제어권을 넘겨받을 코드에서 call/apply 메서드의 첫 번째 인자에 콜백 함수 내부에서의 this가 될 대상을 명시적으로 바인딩하기 때문이다.
(thisArg || window)

4 - 6 : 콜백 함수 내부에서의 this
    setTimeout에 넘겨진 function은 내부에서 콜백 함수르 호출할 시 call 메서드의 첫 번째 인자에 전역객체를 넘기기 때문에 콜백 함수 내부에서 this가 window를 가리킴. forEach는 별도의 인자로 this를 받는 경우에만 this가 변경되지만 별도의 인자로 넘겨주지 않았기 때문에 window를 출력함. addEvenetListener는 내부에서 콜백 함수를 호출할 때 call 메서드의 첫 번째 인자에 addEvenetListener메서드의 this를 그대로 넘기도록 정이돼 있음. 따라서 호출한 주체인 HTML엘리먼트인 '<button id="a">클릭</button>' 이 출력됌.

4 - 7 : 메서드를 콜백 함수로 전달한 경우
    위 코드에서 중요한 라인은 미자믹라인인 [4, 5, 6].forEach(obj.logValues)이다. 콜백 함수로 어떤 객체의 메서드를 전달하더라도 그 메서드는 메서드가 아닌 함수로서 호출이된다는 것이다. 출력값으로 forEach에 this는 따로 넘겨주지 않았기 때문에 window 시작부부인 첫째 값과 인덱스를 출력하였다.

4 - 8 : 콜백 함수 내부의 this에 다른 값을 바인딩하는 방법(1) - 전통적인 방식
    obj1객체 내부에 var self = this를 선언하여 self변수에 this를 저장하도록 하였다. 그리고 var callback = obj1.func()를 선언하고 setTimeout함수에 콜백 함수로 callback을 넘겨 출력 값을 확인하면 1초 후 this는 obj1을 출력하게 된다.

4 - 9 : 콜백 함수 내부에서 this를 사용하지 않은 경우
    this를 사용하지 않고 obj1.name을 직접사용하여 setTimeout에 콜백함수의 인자로서 넘겨주어 출력값을 확인하는 코드이다.

4 - 10 : 예제 4 - 8의 func함수 재활용
    
    
    
# JS_CH4
