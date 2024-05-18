# JS_CH4
4 - 1 : 콜백 함수 예제(1-1) setInterval
    콜백함수 제어권에 관련된 예제이다. setInterval에 첫번째 인자로 무기명함수를 넘겨주었다. 0.3초마다 timer실행 count가 4를 넘기면 clearInterval 호출 및 종료

4 - 2 : 콜백 함수 예제(1-2) setInterval
    4 - 1의 예제코드를 보기쉽게 변경하였고 동작원리는 같다.

4 - 3 : 콜백 함수 예제(2-1) Array.prototype.map
    newArr를 변수로서 선언 후 map함수를 할당하였고 인자로 함수를 넘겨주었다. 넘겨받은 인자는 currentValue, index를 인자로 갖는다. map 함수는 Array.prototype의 메서드로써 기본으로 받는 인자는 currnetValue, index, array를 받지만 본 코드에서는 마지막 array를 생략하였다. 

4 - 4 : 콜백 함수 예제(2-2) : Array.prototype.map - 인자의 순서를 임의로 바꾸어 사용한 경우
    임자의 순서를 임의로 바꾸어 사용할 수 없다. 본 코드에서 map의 인자로 받는 currentValue와 index의 순서를 바꾸었다. 하지만 이는 이름만 바뀐 것이고 map이 받는 인자순서는 변경되지 않기 때문에 결과값은 4 - 3과 달라진다. 
# JS_CH4
