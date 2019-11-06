# React Hook

`React 16.8`에 업데이트 된 기능. Class를 이용해야만 State와 LifeCycle 함수에 접근이 가능했지만, Hook을 사용하면 **함수**에서도 State를 사용 가능!



### Hook의 특징

- **선택적 사용**, 기존의 코드를 재작성하지 않아도 된다.

- **이전 버전과 호환 가능**



### 기존 문제점

- 컴포넌트 사이에서 State와 관련된 로직을 재사용하기 힘듦.

- 복잡한 컴포넌트를 이해하기 어려움.

- Javascript Class의 급격한 러닝 커브.

  ##### → Hook을 사용하면 해결 가능!



## 사용법

#### useState()

```javascript
import React, { useState } from 'react';

function Example() {
  // "count"라는 새 상태 변수를 선언합니다
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```



useState()를 포출하면 현재 State 값과 State르 업데이트 할 수 있는 함수를 return한다. 이 함수를 호출하면 State를 변경할 수 있다.