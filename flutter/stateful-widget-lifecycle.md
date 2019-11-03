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



#### 5. build()

매우 자주 호출되는 메소드다. `@override`를 사용하고 Widget 클래스를 반드시 반환해야 한다.



#### 6. didUpdateWidget(Widget oldWidget)

didUpdateWidget()은 부모 위젯이 변경되며 위젯이 rebuild 될 때 호출된다. 그리고 rebuild 하는 동안 같은 runtimeType을 가지고 있을 경우 호출된다.



#### 7. setState()

State가 변경되었음을 알리는 메소드. setState()가 호출되면 위젯은 buildContext를 rebuild한다.

- setState()는 비동기 사용이 불가능한 함수를 콜백으로 받는다. 



#### 8. deactivate()

deactivate()는 State가 트리에서 삭제될 대 호출되지만, 현재 프레임이 변경되기 전에 재사용될 수 있다.



#### 9.dispose()

dispose()는 State가 삭제될 때 호출된다. 이 메소드를 호출하면 애니메이션, 스트림 등을 취소할 수 있다.



#### 10. mounted == false

State가 unmount되면 절대 remount 할 수 없다. BuildContext 내부의 `bool this.mounted`를 false로 바꾼다.