<template>
  <h1 @click="increase">
    <!-- JS에서 오는 데이터라는 의미로 중괄호 두개 입력 -->
    {{ count }}
  </h1>
  <div v-if="count > 4">
    4보다 큽니다!
  </div>
  <ul>
    <Fruit
      v-for="fruit in fruits"
      :key="fruits"
      :name="fruit">
      <!-- fruits의 아이템 갯수만큼 반복됨 (3번 반복) -->
      <!-- 배열의 아이템을 반복하면서 그것을 fruit라는 변수에다가 할당해서, 그 변수를 li태그 내부에서 데이터로 활용 -->
      <!-- 데이터를 반복할 때는 각각의 데이터가 고유한지를 증명하기 위해 :key 라는 속성을 제공해줘야함 -->
      {{ fruit }}
    </Fruit>
  </ul>
</template>

<script>
import Fruit from'~/components/Fruit'

export default {
  components: {
    Fruit // 가져와서 사용할 이름: 가져올 컴포넌트 이름 (두개의 이름이 같다면 콜론 뒤쪽 생략 가능)
  },
  data() { 
  // data: function() 에서 콜론과 function 키워드가 생략된 것
    return {
      count: 0,
      fruits: ['Apple', 'Banana', 'Cherry']
    }
  },
  methods: {
    increase() {
    // increase: function() 에서 콜론과 function 키워드가 생략된 것
      this.count += 1 // this는 sciprt 부분을 지칭함
    }
  }
}
</script>

<style lang="scss">
  h1 {
    font-size: 50px;
    color: royalblue;
  }
  ul {
    li {
      font-size: 40px;
    }
  }
</style>

