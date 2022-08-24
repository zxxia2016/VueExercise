<template>
  <div id="app">
    <Header />
    <div class="container">
      <Input />
      <List :comments='comments' />
    </div>
  </div>
</template>

<script>
import Header from './comment/Header'
import Input from './comment/Input'
import List from './comment/List'
export default {
  name: 'App',
  components: {
    Header,
    Input,  
    List
  },
  data () { 
    return {
      comments: [
        { name: 'bob', content: 'so easy' },
        { name: 'cat', content: 'good' },
        { name: 'bz', content: 'so so' }
      ]
    }
  }
}
</script>

<style>
</style>
