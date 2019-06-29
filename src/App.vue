<template>
  <div id="app">
    <jsx-test :count="count" class="test" @click="clickHandler"/>
    <TestJsx :count="count" :text="123" @update="newInfo = $event">
      <template v-slot:s1>
         <div>slot</div>
      </template>
      <template v-slot:s3="{ name }">
         <div>{{name}}</div>
      </template>
    </TestJsx>
    {{newInfo}}
  </div>
</template>

<script>
import Test from './components/testfun.vue';
import TestJsx from './components/testjsx.vue';


export default {
  name: 'app',
  data(){
    return {
      count: 88,
      newInfo: '',
    }
  },
  components: {
    'jsx-test': Test,
    TestJsx
  },
  methods: {
    clickHandler(){
      alert(999)
    }
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
