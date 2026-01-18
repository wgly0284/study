<details><summary>1강</summary>

## React 시작

```
npm create vite@latest (폴더명)
Select a framework -> React 선택
```

</details>


<details><summary>2강</summary>

## JS 복습 ①

```
<script>
class Car {
  constructor(car_brand) {
    this.brand = car_brand;
  }
}
const ycar = new Car("Hyundae");
console.log(mycar.brand);
</script>
```

- `constructor`: `new` 키워드로 호출하면 자동으로 호출되는 함수. 생성자 함수라고도 함.


```
<script>
class Car {
  constructor(car_brand) {
    this.brand = car_brand;
  }
  hello() {
    return `제 차 브랜드명은 ${this.brand} 입니다.`
  }
}
const mycar = new Car("Hyundae");
let a = mycar.hello();
console.log(a);
</script>
```
- `let`으로 변수 지정해서 호출하는 방법


```
<script>
class Car {
  constructor(car_brand) {
    this.brand = car_brand;
  }
  hello() {
    return `제 차 브랜드명은 ${this.brand} 입니다.`
  }
}

class Model extends Car {
  constructor(car_brand, car_model) {
    super(car_brand);  // super를 통해 부모클래스의 생성자를 호출해서 세팅해줘야 함.
    this.model = car_model;
  }
  hi() {
    return this.hello() + `, 차종은 ${this.model} 입니다.`;
  }
}
const mycar = new Model("Hyundae", "Genesis");
let a = mycar.hi();
console.log(a);
</script>
```

- Car 클래스의 메서드를 상속 받는 Model이라는 클래스를 만드는 방법.
- `super`를 통해서 부모 클래스의 `constructor`를 호출했고, 브랜드 값이 초기화되는 방식


</details>

<details><summary>3강</summmary>

## JS 복습 ② 화살표 함수

- 기본 사항

```
<script>
hello = function() {
  return "오랜만의 JavaScript 가 반가워요."
}
let a = hello();
console.log(a)
</script>
```

- 화살표 함수

```
<script>
hello = () => {
  return "오랜만의 JavaScript 가 반가워요."
}
let a = hello();
console.log(a)
</script>

```

- 화살표 함수 + 매개변수
```
<script>
hello = (val) =>  `오랜만의 ${val}$ 가 반가워요.`

let a = hello('JavaScript');
console.log(a)
</script>
```

- ???
```
<script>
const obj = {
  name: '왕초보 홈페이지 만들기',
  normalFunc: function() {
    console.log("normalFunc this.name : ", this.name");
  }
  arrowFunc: () => {
    console.log("arrowFunc this.name: ", this.name) ;
  }
}

obj.normalFunc ();
obj.arrowFunc();
</script>
```
- 일반적인 함수에서 `this`는 객체 내의 `name`을 가리키나, arrowFunc을 사용 시 windows 객체를 가리킴.

</details>