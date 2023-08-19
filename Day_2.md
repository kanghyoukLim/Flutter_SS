20230819 

## 기본 앱 레이아웃

### 유용한 MaterialApp() 위젯
MaterialApp()은 구글이 제공하는 디자인 클래스, 이 것을 사용하면 코드 작성을 쉽게 할 수 있다.

Material Design 쓰려면 일단 pubspec.yaml 파일에 이런 항목이 켜져있어야 함 
```
flutter:
  uses-material-design: true 
```

Scaffold()는 화면을 상중하로 나눠주는 위젯
```
MaterialApp(
  home: Scaffold(
    appBar: 상단에 넣을 위젯,
    body: 중단에 넣을 위젯,
    bottomNavigationBar: 하단에 넣을 위젯,
  )
);
```
상단바 하단바는 없어도 상관없지만, body는 필수 

```
MaterialApp(
  home: Scaffold(
    appBar: AppBar( title: Text('앱제목') ), 
    body: Text('안녕'), 
    bottomNavigationBar: BottomAppBar( child: Text('하단바') ),
  )
);
```
파라미터 찾는 것은 ctrl + space

위젯 여러개를 가로, 세로 배열할 때는 Row() 또는 Column() 위젯과 children: 파라미터를 사용
```
MaterialApp(
  home: Scaffold(
    body: Row( 
      children: [ Icon(Icons.star), Icon(Icons.star), Icon(Icons.star) ] 
    ), 
  )
);
```

### 가로 간격 조절
```
MaterialApp(
  home: Scaffold(
    body: Column( 
      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
      children: [ Icon(Icons.star), Icon(Icons.star), Icon(Icons.star) ] 
    ), 
  )
);
```
.spaceEvenly 는 모든 여백 동일
.spaceBetween 은 좌우 끝에 우선 배치
.spaceAround는 모든 여백 동일인데 좌우 마지막 여백은 절반만큼
.start는 시작 부분에 다 모여
.end는 끝 부분에 다 모여
.center는 중간에 다 모여 
. 찍고 자동완성으로 이용

### 세로 간격 조절
```
body: Container (
  color: Colors.grey,
  height : 400,  //높이 넣어야 세로정렬 가능할듯 
  child : Row (
    crossAxisAlignment: CrossAxisAlignment.start,
    children: const [
      Icon(Icons.star),
      Icon(Icons.star),
      Icon(Icons.star),
    ],
  ),
),
```
