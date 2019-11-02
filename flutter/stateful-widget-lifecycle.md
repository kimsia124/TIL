# Stateful Widget LifeCycle

Stateful 위젯은 위젯의 LifeCycle 동안 변경 될 수 있는 상태를 유지하는 위젯이다.



#### State의 개념

- 위젯에서 사용되는 데이터이며 변화함.
- 위젯을 Build 할 때 동기식으로 읽을 수 없음.



#### Stateful Widget LifeCycle steps:

1. createState()
2. mounted == true
3. initState()
4. didChangeDependencies()
5. build()
6. didUpdateWidget()
7. setState()
8. deactivate()
9. dispose()
10. mounted == false



#### 1. createState()

Stateful  Widget이 build 될 때, 반드시 createState() 함수를 override하고 실행해야한다.

```dart
class MyStatefulPage extends StatefulWidget{
    @override
    _MyStatefulPage createState() = _MyStatefulPage();
}
```



#### 2. mounted == true

createState() 함수가 실행되면, BuildContext에 state가 할당된다.

모든 Widget에는 `bool this.mounted`라는 property가 존재한다. 이 property가 true가 될 때, BuildContext가 할당된다. `mounted != true`일 경우 setState() 하지 못한다.



#### 3. initState()

initState()는 오직 한 번 사용된다. 반드시 `super.initState()`와 사용해야 한다.



#### 4. didChangeDependencies()

didChangeDependencies 메소드는 위젯이 build될 때, initState()가 실행된 후 실행된다.

build 메소드는 항상 didChaneDependencies가 호출 된 뒤에 호출된다.