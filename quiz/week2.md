## 문제 1

자바스크립트에서 원시 값(primitive value)과 객체(object)의 변수 할당 방식의 차이를 설명해 보세요.

**원시 값 (Pass by Value):**  
 원시 값(예: `number`, `string`, `boolean`, `null`, `undefined`, `symbol`, `bigint`)은 변수에 할당할 때 실제 값이 복사됩니다.

**객체 (Pass by Reference):**  
 객체는 변수에 할당할 때 해당 객체의 **참조(메모리 주소)** 가 복사됩니다.

## 문제 2

함수에 원시 값과 객체를 인자로 전달할 때, 함수 내부에서 해당 인자를 수정하면 외부에 어떤 영향이 미치는지 설명해 보세요. 예제 코드를 포함해서 답변해 주세요.

**원시 값의 경우 (값에 의한 전달):**  
 함수에 원시 값을 인자로 전달하면 복사본이 전달됩니다.  
 함수 내부에서 이 값을 변경해도 원래 변수에는 영향을 주지 않습니다.

```
function changePrimitive(val) {
    val = 100;
}
let num = 50;
changePrimitive(num);
console.log(num); // 출력: 50
```

**객체의 경우 (참조에 의한 전달):**  
 객체를 함수에 전달하면 객체의 참조가 전달되므로 함수 내부에서 객체의 프로퍼티를 변경하면 외부 객체에도 영향을 미칩니다.  
 단, 함수 내부에서 객체 전체에 재할당하는 경우에는 외부 객체에는 영향을 주지 않습니다.

```
function modifyObject(obj) {
  obj.name = 'Park';
}
let person = { name: 'Lee' };
modifyObject(person);
console.log(person.name); // 출력: Park
```

```
function reassignObject(obj) {
  obj = { name: 'Choi' };
}
let person = { name: 'Lee' };
reassignObject(person);
console.log(person.name); // 출력: Lee
```
