# Flutter_SS
20230818 written by KH.Lim
Flutter 코딩애플 강의요약

## 시작하기 전에 Lint 관련 워닝 무시하는 법 
 

Flutter 2.5 버전 이후 부터는 Lint 생김
Lint는 잘못된 부분을 교정하라는 표시, 초보는 하나하나 지켜가며 코딩하기에 어려움 

그래서 analysis_options.yaml 파일 열어서 


(analysis_options.yaml)

```Flutter
rules:
  prefer_const_constructors: false
  avoid_print: false
  prefer_typing_uninitialized_variables: false
  prefer_const_constructors_in_immutables: false
```

이걸 추가해두고 시작하면 Lint 경고가 뜨지 않음 

(주의) rules: 보다 prefer어쩌구: 가 스페이스바 2개만큼 앞에 있어야합니다.
 

## 앱만들기
1. 코드는 lib 폴더 안에 main.dart 파일에 짜면 됨.

```Flutter
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}
```
요것만 남기고 모두 삭제

runApp() 이건 "앱 시작해주세요~" 라는 기본 함수
runApp() 소괄호 안에 우리가 만든 앱 레이아웃을 넣으면 앱으로 보여줌

## 메인페이지 만들기
runApp 중괄호 아래에 stless 입력 후 탭키 치면 기본코드 생성되고,
```
class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);
  @override
  Widget build(BuildContext context) {

    return MaterialApp(
      home: Text('안녕'),
    );

  }
}
```
class 다음에 'MyApp' 입력
자동생성코드에는 return Container(); 가 생성되는데, 
Container를 MaterialApp 으로 바꿔줌
자동완성코드는 기본값으로 이해하면 되고, 
return 이하가 실제 구현되는 앱 모양임.

## 디자인 해보기

Flutter 개발방식은 위젯() 사용하는것 
글자 넣고 싶으면 Text() 이미지 넣고 싶으면 Image() 네모박스 넣고 싶으면 Container() 

Flutter에서 위젯 4개만 잘 외워두면 거의 모든 레이아웃을 만들 수 있음
글자, 이미지, 아이콘, 박스 이렇게 4개 위젯

### 글자넣는 Text()
```
MaterialApp(
  home: Text('안녕')
)
```
작동확인은 에뮬레이터에서 크롬 선택 후 플레이 해보면 크롬웹브라우저에서 실행되는 것이 확인 됨.

### 아이콘 넣을땐 Icon()
```
MaterialApp(
  home: Icon(Icons.star)
)
```
아이콘 이름은 https://api.flutter.dev/flutter/material/Icons-class.html 여기서 찾으면 됨. 
