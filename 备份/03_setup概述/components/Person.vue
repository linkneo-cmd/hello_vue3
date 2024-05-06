<template>
    <div class = "person">
        <h2>姓名：{{name}}</h2>
        <h2>年龄：{{age}}</h2>
        <button @click = "changeName">修改名字</button>
        <button @click = "changeAge">修改年龄</button>
        <button @click = "showTel">查看联系方式</button>
    </div>
</template>

<script lang = "ts">
    export default {
      name: 'Person',
      setup(props, ctx) {
        //setup函数中的this是undefined，vue3中已经弱化this了
          //数据，原来是写在data中，此时的name、age、tel不是响应式的
          let name = '张三';
          let age = 25;
          let tel = '13812345678';
         //方法
         function changeName() {
            name = 'zhangsan1'//注意这样修改name是没有变化的，name确实改了，但name不是响应式的
          }
          function changeAge() {
            age += 1
          }
          function showTel() {
            alert(tel)
          }
          return {
              name,
              age,
              changeName,
              changeAge,
              showTel
          }
 
      }
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