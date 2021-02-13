## 📆 2월 13일 공부 기록

### 뷰 인스턴스

    Vue.js를 사용하여 웹 페이지에 필요한 기능을 만들 때 기본적으로 생성해야 하는 객체

### 기본 형식

```html
...
<body>
  <div id="app">
    {{ message }}
    <!-- Hi from Vue.js 출력 -->
  </div>
</body>
```

```javascript
new Vue({
  // properties...
  data() {
    return {
      message: "Hi from Vue.js",
    };
  },
}).$mount("#app");
// #app에 연결하여 DOM 제어
```

### 뷰 속성

#### template

    HTML 엘리먼트, 스타일 등을 설정하는데 사용하는 속성

#### methods

    이벤트 처리와 같은 동적인 작업을 처리하는 속성
    명시적인 호출로 실행

#### computed

    뷰 인스턴스 내의 데이터를 조작하는 속성
    데이터의 변화를 감지하여 자동으로 계산

#### props
    다른 컴포넌트로 데이터를 전달하는 속성

#### watch
    data 객체 내의 데이터의 변화를 감지하여 자동으로 후속 처리를 해주는 속성

### 뷰 라이프 사이클

1. 인스턴스 생성 : new Vue로 객체 초기화
2. beforeCreate : 이벤트 / 라이프 사이클 초기화
3. created : 

| 단계 | 내용 |
| ----- | ---- |
| new Vue() | 이벤트 및 라이프 사이클 초기화 |
| beforeCreate | 화면에 반응성 주입
| created | el, template 속성 확인, <br> template 속성을 render() 로 변환 |
| beforeMount | $el 생성, el 속성 값 대입 |
| mounted | 인스턴스를 화면에 부착 |
| beforeUpdate | 화면 재렌더링 및 데이터 갱신 |
| updated | 인스턴스 내용 갱신 |
| beforeDestroy | 컴포넌트, 인스턴스, 디렉티브 해제 |
| destroyed | 인스턴스 소멸

* beforeUpdate, updated 단계는 데이터 변경이 있을 경우에만 실행
* updated 단계까지 인스턴스에 접근 가능