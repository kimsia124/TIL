# Passing Data to StatefulWidet

Flutter에서 StatelessWidget으로 데이터를 넘기려면 `constructor`를 사용한다.



``` dart
class TodosScreen extends StatelessWidget {
  final int num;

  TodosScreen({Key key, @required this.num}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    ...
  }
}

TodoScreen(num: 0);
```



StatefulWIdget으로 데이터를 넘길 때는 StatefulWidget과 StateWidget이 분리되기 때문에 이 방법을 사용할 수 없다. `widget.variable`을 사용해야 한다.



```dart
class _TodoScreenState extends State<TodoScreen> {
  @override
  Widget build(BuildContext context) {
   .....
   widget.num
   .....
  }
}
```

