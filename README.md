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
