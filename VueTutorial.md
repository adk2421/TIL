# Vue.js 따라하기

API 스타일 : 옵션, SFC
> SFC(Single File Component) : HTML, CSS, JavaScript를 캡슐화한 코드 블록으로 재사용 가능한 `.vue` 파일입니다.

<br>

### 선언적 렌더링 [# Vue.js Tutorial-2](https://v3-docs.vuejs-korea.org/tutorial/#step-2)
Vue의 핵심 기능은 **선언적 렌더링**입니다. HTML을 확장하는 템플릿 문법을 사용하여 JavaScript 상태를 기반으로 HTML이 어떻게 보이는지 설명할 수 있습니다. 상태가 변경되면 HTML이 자동으로 업데이트됩니다.

변경 시, 업데이트를 트리거할 수 있는 상태는 **반응형**으로 간주됩니다. Vue에서 반응형 상태는 컴포넌트에 유지됩니다.

컴포넌트에서 객체를 반환해야하는 함수 `data` 옵션을 사용하여 반응형 상태를 선언할 수 있습니다:

```
<script>
export default {
  data() {
    return {
      message: '안녕 Vue!',
      counter: {
        count: 3
      }
    }
  }
}
</script>

<template>
  <!-- JavaScript 표현식 사용 가능 -->
  <h1>{{ message.replace('안녕', 'Hello') }}</h1>
  <p>숫자 세기: {{ counter.count }}</p>
</template>
```

결과
># Hello Vue!
숫자 세기: 3

<br>

### 속성 바인딩 [# Vue.js Tutorial-3](https://v3-docs.vuejs-korea.org/tutorial/#step-3)
Vue에서 이중 중괄호는 텍스트 삽입에만 사용됩니다. 속성을 동적 값에 바인딩하려면 `v-bind` 디렉티브를 사용합니다.

**디렉티브**는 v- 접두사로 시작하는 특수한 속성으로 Vue 템플릿 문법의 일부입니다. 텍스트 삽입과 유사하게 디렉티브 값은 컴포넌트의 상태에 접근할 수 있는 JavaScript 표현식입니다.

콜론(`:`) 뒤의 부분(`class`)은 디렉티브의 "인자"입니다. 여기서 엘리먼트의 `class` 속성은 컴포넌트 상태의 `titleClass` 속성과 동기화됩니다.

>v-bind는 너무 자주 사용되기 때문에 전용 단축 문법이 있습니다.
`v-bind:class="titleClass"` → `v-bind:class="titleClass"`

```
<script>
export default {
  data() {
    return {
      titleClass: 'title'
    }
  }
}
</script>

<template>
  <h1 :class="titleClass">글자색 변경</h1>
</template>

<style>
.title {
  color: red;
}
</style>
```

결과
># <span style="color:red">글자색 변경</span>

<br>

### 이벤트 리스너 [# Vue.js Tutorial-4](https://v3-docs.vuejs-korea.org/tutorial/#step-4)

```
<script>
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    increment() {
      this.count++
    },
    reset() {
      this.count = 0
    }
  }
}
</script>

<template>
  <button @click="increment">숫자 세기: {{ count }}</button>
  <button @click="reset">초기화</button>
</template>
```
