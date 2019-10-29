# Flutter에서 Row 안에 TextField 넣기

#### Row children으로 TextField를 넣으면?

예를 들어, 다음과 같이 코드를 작성할 경우:

```dart
Row(
  children: <Widget>[
    TextField(),
  ]
)
```



build 시 다음과 같은 에러 발생:

```
D8: Program type already present: io.flutter.BuildConfig
com.android.builder.dexing.DexArchiveMergerException: Error while merging dex archives: 
Learn how to resolve the issue at https://developer.android.com/studio/build/dependencies#duplicate_classes.
Program type already present: io.flutter.BuildConfig
	at com.android.builder.dexing.D8DexArchiveMerger.getExceptionToRethrow(D8DexArchiveMerger.java:131)
	at com.android.builder.dexing.D8DexArchiveMerger.mergeDexArchives(D8DexArchiveMerger.java:118)
	at 
	
.
.
.

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':app:mergeExtDexDebug'.
> A failure occurred while executing com.android.build.gradle.internal.tasks.Workers$ActionFacade
   > com.android.builder.dexing.DexArchiveMergerException: Error while merging dex archives: 
     Learn how to resolve the issue at https://developer.android.com/studio/build/dependencies#duplicate_classes.
     Program type already present: io.flutter.BuildConfig

* Try:
Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output. Run with --scan to get full insights.

* Get more help at https://help.gradle.org

BUILD FAILED in 59s
Finished with error: Gradle task assembleDebug failed with exit code 1
```



### 해결방법

Flexible, 혹은 Expanded 안에 TextField를 넣는다.

예를 들어, TextField와 RaisedButton을 함께 사용하고 싶은 경우:

```dart
Row(
  children: <Widget>[
    Flexible(
      flex: 5,
      child: TextField(),
    ),
    Flexible(
      flex: 1,
      child: RaisedButton(
        child: Text('flutter'),
      ),
    ),
  ],
)
```



### Why?

Row 위젯은 자식 위젯의 사이즈가 정해져야 한다(Non-Flexible).

하지만 TextField 위젯은 크기가 정해져 있지 않고 부모 위젯의 전체 폭과 크기를 동일하게 유지한다.

Flexible or Expanded 위젯으로 TextField 위젯의 폭을 결정해주면 Row, Column 모두 사용할 수 있다.