# UTF-8 with BOM

유니코드 인코딩 간 구별은 **Byte Order Mark (BOM)**을 사용한다. 문서 맨 앞에 특정 바이트를 넣어 인코딩 방식을 구분한다. 하지만 UTF-8 인코딩 방식에서 BOM이 문제를 일으킬 수 있다.



## UTF-8 with BOM으로 생기는 문제

일부 텍스트 에디터는 텍스트 파일을 생성할 때 자동으로 BOM을 삽입한다. BOM의 유무로 인해 파일이 달라 보일 수 있다.



| 인코딩 방식 | BOM (Byte Order Mark) |
| :---------- | --------------------- |
| UTF-8       | `EF BB BF`            |
| UTF-16      | `FE FF`               |
| UTF-32      | `00 00 FE FF`         |



UTF-16과 UTF-32 인코딩은 BOM의 배열 순서로 Big Endian, Little Endian을 구분하지만 UTF-8은 순서가 정해져있다. BOM이 없어도 자동으로 인코딩 방식을 알아낼 수 있으며 일반적으로 프로그래밍에 사용되는 파일에는 BOM을 포함하지 않는다.