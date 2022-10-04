<template>
  <div>
    <img v-for="item in testData" :key="item.url" :src="item.url" alt="">
  </div>
</template>

<script>

export default {
  name: 'HomePage',
  data() {
    return {
      testData:[]
    }
  },
  async fetch({$axios}) {
    const res = await $axios.get('https://vue-lessons-api.herokuapp.com/photo/list')
    console.log(res);
    this.testData = res.data;
    console.log(this.testData)
  }
}
</script>