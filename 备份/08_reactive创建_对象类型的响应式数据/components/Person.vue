<template>
    <div class = "person">
      <h2>一辆{{ car.brand }}车，价值{{ car.price }}万元</h2>
      <button @click="changePrice">修改汽车的价格</button>
      <br/>
      <h2>游戏列表：</h2>
      <ul>
        <li v-for="g in games" :key="g.id">{{ g.name }}</li>
      </ul>
      <button @click="changeFirstGame">修改第一个游戏名字</button>
    </div>
</template>

<script lang = "ts" setup name = "Person">
  import {handleError, reactive} from 'vue'
  let car = reactive({ brand: '凯迪拉克', price: 100 })

  let games = reactive([
    { id: 1, name: '王者荣耀' },
    { id: 2, name: '绝地求生' },
    { id: 3, name: '刺激战场' }
  ])

  function changePrice() {
    car.price += 10
  }

  function changeFirstGame(){
    games[0].name = '原神'
  }
</script>

<style scoped>
    .person {
        background-color: skyblue;
        box-shadow: 0 0 10px;
        border-radius: 10px;
        padding: 20px;
        font-size: 20px;  
    }
    button {
        margin: 0 5px;
    }
</style>