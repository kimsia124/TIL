# Custom Slider Thumb

Flutter에서 Slider Thumb를 Custom하려면 `SliderComponentShape`를 extend 해야한다. `paint()` 메소드로 Thumb를 그릴 수 있다.



## How to Draw?

```dart
canvas.drawCircle(Offset, radius, paint);
```

offset\<Offset>: 좌표

radius\<double>: 반지름

paint\<Paint>: paint 함수



#### Fill Color

```dart
final fillPaint = Paint()
  ..color = Colors.white
  ..style = PaintingStyle.fill;
```



#### Border Color

```dart
final borderPaint = Paint()
   ..color = sliderTheme.activeTickMarkColor
   ..strokeWidth = 6.0
   ..style = PaintingStyle.stroke;
```