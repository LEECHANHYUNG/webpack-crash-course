> Webpack을 쓰는 이유는 무엇일까?

1. 모듈 번들링

- 여러 Javascript 파일과 의존성 모듈들을 하나의 또는 소수의 파일로 묶어준다.
- 이를 통해 네트워크 요청 횟수를 줄여 초기 로딩 속도 향상

### 1. 모듈 이전의 상황

- 초기 Javacript에는 내장된 모듈 시스템이 없어 다음과 같은 문제가 발생했다.

1. 전역 스코프 오염
2. 의존성 관리의 어려움
3. 코드 구조화와 재사용성 저하

### 2. IIFE(Immediately Invoked Function Expression

- 즉시 실행 함수 표현
  - 정의되자마자 즉시 실행되는 Javascript function
- private scope를 생성하고 전역 오염을 방지했지만, 의존성 관리에는 여전히 한계가 있었다.

### 3. CommonJS와 AMD

1. **CommonJS**

- 서버 사이드 Javascript를 위해 설계되었으며, 동기적 모듈 로딩을 사용
  ```jsx
  const circle = require("./circle.js");
  console.log(circle.area(4));
  ```

1. AMD (Asynchronous Module Definition)

- 브라우저 환경을 위해 설계되었으며, 비동기적 모듈 로딩을 지원
  ```jsx
  define(["./circle"], function (circle) {
    console.log(circle.area(4));
  });
  ```

---

### 하지만 아직까지 모든 브라우저에서 지원하지 않아 브라우저와 무관하게 사용할 수 있는 모듈이 필요 - Webpack의 필요성

1. 통합된 모듈 시스템
   - CoomnonJS, AMD, ES6 모듈 등 다양한 모듈 형식을 지원한다.
2. 의존성 관리
   - 모든 의존성을 자동으로 추적하고 관리
3. 코드 분할과 최적화
   - 필요한 코드만 로드하여 성능 개선
4. 자산 관리
   - Javascript 뿐만 아니라 CSS, 이미지 등 다양한 자산을 모듈로 처리 가능
5. 개발 환경 개선
   - 핫 모듈 리로딩 등의 기능으로 개발 환경 향상
6. 브라우저 호환성
   - 최신 Javascipt 기능을 구버전 브라우저에서도 사용할 수 있게 한다.
