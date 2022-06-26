<template>
  <div>

    <h2>vue</h2>
    <ul>
      <li v-for="(n, i) in menus" :key="i"><a href="#">{{i}}___{{n}}</a></li>
    </ul>

    <p v-for="(v, i) in products" :key="i">
      {{v}}

      <button :class="[i+'_btn']" @click="count1++">click</button>
      <button :class="[i+'_btn']" @click="increase">click</button>
      
      <span>count : <span :class="[i+'_count']">{{count1}}</span></span>
    </p>

  </div>
</template>

<script>
let val = [];
for (let i = 0; i < 5; i++) {
  val[i] = i+1;
}

export default {
  name: 'FirstVue',

  data(){
    //데이터 보관함
    return {
      count1 : 0,
      menus : ['Home', 'Shop', 'About'],
      //products : [1,2,3,4,5]
      products : val
    }
  },

  methods : {
    increase(){
      //data의 내용을 사용하기 위해서는 this를 사용해서 불러온다.
      this.count1 += 1;
    }
  },

}
</script>

<style scoped>
  ul {display: flex;}
  li {flex-direction: row; flex-wrap: wrap; justify-self: center;
  justify-content: center; align-items: center; width: 33.3%; text-align: center;} 
</style>
