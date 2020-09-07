# Type Coercion

먼저 아래 있는 코드의 결과를 예측할수 있나요?

```javascript
console.log(4 + "hello");
console.log(4 + 4 + "hello");
console.log("" == true);
console.log(1 == true);
console.log(66 + true);
```

결과는 다음과 같습니다

```javascript
console.log(4 + "hello");     //4hello
console.log(4 + 4 + "hello"); //8hello
console.log("" == true);      //false
console.log(1 == true);       //true
console.log(66 + true);       //67
```

마지막의 결과가 좀 충격적이지 않나요? 

그렇다면 도대체 왜!! 이런 결과가 나오는 것일까요

결과들이 조금 예측을 벗어났을 수도 있지만, 이러한 걸로 인해 우리는 JS를 편하게 사용할 수 있습니다. 

즉 우리가 이상한걸 만들었지만,  똑똑한 JavaScript는 그걸 계산해 준것이죠..

이런걸 바로 Type Coercion 즉, **강제 형변환**이라고 합니다.



### 강제 형변환

`66+true`를 보면 JavaScript는 true를 1로 강제로 형변환 시켜줘서 67이라는 결과가 나온답니다.

그렇다면 false는 몇이 나올까요? 

> true: 1
>
> false: 0

이렇게 형변환이 됩니다. 물론 사칙연산 모두가 가능하죠.

자 그럼 아래 코드를 볼까요? 

```javascript
console.log(10 + 10 + true);
```

결과는 21입니다. 숫자 10 + 숫자 10 + true\(1\) 이 계산되는 것이죠. 

또한, + 에서는 loaded operator가 발동됩니다. 

### loaded operator

```javascript
console.log(4 + "hello");     //4hello
console.log(4 + 4 + "hello"); //8hello
```

이렇게 문자열 값과 더하기를 하게 되면 JS는 4를 '4'로 바꿔서 계산해 줍니다. 

즉 아래와 같이 해석되는 것이죠

```javascript
console.log("4" + "hello");     //4hello
console.log("8" + "hello");     //8hello
```

오직 더하기에서만 이렇게 loaded operator가 발동된답니다. 

빼기의 경우에는 반대의 경우가 된답니다. 한번 볼까요?

```javascript
console.log(23 - "1"); //22
//          23 -  1
```

복잡해 보이지만 몇번 직접 해보면 쉽게 이해할 수 있을 것입니다. 

자, 이제 빈 문자열이 왜 false가 나오는지 알아야 겠죠?

이걸 알기 위해서는 **Truthy** 와 **Falsy** 한 값에 대해서 알아둘 필요가 있습니다. 

Truthy 한 값은 음.. true로 보면 되고 Falsy 한 값은 false로 보면 되는데, 

몇가지 대표적인 예를 보여드릴게요.

### Falsy한 값

```javascript
console.log(!undefined); //true
console.log(!null);      //true
console.log(!0);         //true
console.log(!'');        //true
console.log(!NaN);       //true
```

모두 !를 붙여서 반대로 나온다는 것을 알아주세요. 

### Truthy한 값

```javascript
console.log(!3);            //false
console.log(!'hello');      //false
console.log(!['array?']);   //false
console.log(![]);           //false
console.log(!{ value: 1 }); //false
```

자 이제 이해가 되었나요? 

그렇다면 처음 나온 빈 문자열이 왜 false가 나오는지도 알 수 있을 것입니다. 

그렇다면 마지막으로 다음의 결과는 어떻게 출력이 될까요?

```javascript
const v = { one: 1 };
const truthy = !!v;
```

> 1. v=truthy한 값. 
> 2. !v 는 false
> 3. !false 는 true

다음에는 Value 와 Reference에 대하여 알아보겠습니다. 

