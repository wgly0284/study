# React 실습


| 측면 | Vue | React |
|------|-----|-------|
|코드|`<template><div><p>Count: {{ count }}</p><button @click="increment">증가</button></div></template><script setup>import { ref } from 'vue';const count = ref(0);const increment = () => { count.value++; };</script>`|`import { useState } from 'react';function Counter() { const [count, setCount] = useState(0); const increment = () => { setCount(count + 1); }; return ( <div> <p>Count: {count}</p> <button onClick={increment}>증가</button> </div> );}`
|반응성 차이|ref.value 변경 시 즉시 추적, 런타임 프록시 기반 |setState로 배치 업데이트, 다음 렌더에서 반영 |
|코드|`	<template><input v-model="name" /><p>Hello, {{ name }}!</p></template><script setup>import { ref } from 'vue';const name = ref('');</script>`|`function Form() { const [name, setName] = useState(''); return ( <div> <input value={name} onChange={(e) => setName(e.target.value)} /> <p>Hello, {name}!</p> </div> );}`
|바인딩 방식|v-model이 자동으로 getter/setter 처리|value/onChange 조합으로 수동 제어 |


## 변환 팁
Vue ref → React useState: .value 제거하고 setState 사용.
​

템플릿 → JSX: {{ }} → { }, @click → onClick.
​

computed/watch → useMemo/useEffect: 의존성 배열로 최적화.
