<template>
  <div id="app">
 <navbar></navbar>
 <todo></todo>
  </div>
</template>

<script>
import navbar from './components/navbar'
import todo from './components/todo'
export default {
  name: 'App',
  components:{navbar,todo}
}
</script>

<style>

</style>
