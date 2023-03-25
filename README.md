# Dart Study

## Defining a Function

void는 함수가 아무것도 return 하지 않는다는 의미, 아래의 함수는 출력만 할 뿐 return을 하지 않는다. 
```dart
void sayHello(String name) {
  print("Hello $name nice to meet you!");
}
```

함수가 출력 대신 어떠한 값을 return 한다면 return하는 값의 타입을 적어준다. like 타입스크립트

```dart
String sayHello2(String name) {
  return "Hello $name nice to meet you!";
}

// 화살표로 축약 가능
String sayHello3(String name) => "Hello $name nice to meet you!";

num plus(num a, num b) => a + b;
```

## Named Parameters

여러개의 파라미터를 받는 함수가 있을때, 순서에 상관 없이 인자를 넘길 수 있다.
```dart
// before
String sayHello(String name, int age, String country) {
  return "Hello $name, you are $age, and you come from $country";
}

void main() {
  print(sayHello('b', 30, 'Korea'));
}

// after: 정의된 함수의 파라미터에 중괄호 추가
String sayHello({String name, int age, String country}) {
  return "Hello $name, you are $age, and you come from $country";
}

void main() {
  print(sayHello(age: 30, country: 'Korea', name: 'b'));
}
```

하지만 Dart의 Null Safety 적용 때문에 에러가 난다. 정의한 파라미터는 3개인데 함수 호출 시
인자를 안보낸다거나 1,2개 보낼 경우에 문제가 되기 때문이다. 두가지 방법으로 해결 가능하다. (null safety에 걸릴 일 X)
+ Default Parameter: 파라미터의 기본값을 설정해준다.
```dart
String sayHello(
    {String name = 'HUBU', int age = 30, String country = 'South Korea'}) {
  return "Hello $name, you are $age, and you come from $country";
}

void main() {
  print(sayHello(age: 30, country: 'Korea', name: 'b'));
}
```

+ required modifier
```dart
String sayHello(
    {required String name, required int age, required String country}) {
  return "Hello $name, you are $age, and you come from $country";
}

void main() {
  print(sayHello(age: 30, country: 'Korea', name: 'b'));
}
```

