<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <li>{{ name }}?!</li> 
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: ''
    }
  }
}
</script>

<style scoped lang="scss"> 
// scoped라는 속성을 사용하면 스타일의 유효범위가 현재 컴포넌트로 잡히게 됨 
// 스타일의 선택자를 복잡하게 작성하지 않아도 손쉽게 스타일 관리 가능
  li {
    font-size: 50px;
    color: red;
  }
</style>
