# Primitive Types

Primitive는 원시적인 의미를 가지고 있습니다. 

즉, 원시 타입이라는 말입니다. 

먼저 원시형 타입에는 총 6가지가 있습니다.

1. String
2. Number
3. Bolean
4. Null
5. Undifined
6. Symbol

### String 

```text
"hello"
'hello'
`hello`
```

같은 모양의 따움표로 시작하고 끝나야 합니다. 

참고로 String안에 "을 작성하고 싶다면 다음과 같이 Escape문자를 작성해주어야 합니다. 

`"Hello my \" name is Yoo \" "`

### Number

```text
110
12.5
-10
```

### Bolean

```text
true
false
```

여기까지는 이해하기 어렵지 않습니다. 

하지만, **undifined 와 null, NaN** 

이 비슷한 것들의 차이점은 무엇일까요? 

* null: 없는걸로 '정의'가 됨
* undifined: '정의'가 되지 않았음

### Undifined

다음과 같은 예시를 들어볼게요

```javascript
let one;
console.log(one); 
```

one이라는 변수를 선언만 해놓고 초기화는 하지 않았지만 , one을 출력해볼까요? 

결과는 **undifined** 입니다. 무슨 의미인지 이해가 되나요?

> null은 아니지만, 아직 정의가 되지 않았다는 의미입니다.

그리고 undifined가 one의 value가 되는 것입니다. 

### null

```javascript
let two = null;
console.log(two); 
```

two는 값이 null이라고 정의가 되어있습니다. 즉, 값이 없죠. 

즉, 그 둘의 차이는 null은 값이 아예 없다!! 이것이고, undifined는 값이 정의되지 않았다!! 이것입니다.

### NaN

Not A Number 이라는 뜻을 가지고 있습니다. 

음.. 수학을 계산해봤을때 식이 잘못되거나 해서 결과가 완전히 꼬여버린 경험이 있으신가요? 

```javascript
function add(a, b) {
  console.log(a * b);
}

add(3, "삼");
```

'숫자' 3과 '문자' 삼을 곱하면 어떻게 될까요? 

말이 안되는 식인가요? 네 맞습니다!

말도 안나오는 숫자계산의 결과물은 바로 **NaN**이 나오는 것입니다.

그렇다면 이러한 type들을 알아내는 방법은 무엇이 있을까요?

**TypeOf** 입니다

### typeOf

```javascript
function one() {
  console.log(typeof "가나다");    //string
  console.log(typeof 1);          //number
  console.log(typeof true);       //bolean
}
one();
```

다음은 Type과 관련된 Type Coercion에 대하여 알아보겠습니다

