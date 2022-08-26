<template>
  <div class="goodNight">
    div
    <p>{{text}}</p>
    <a href="https://github.com/">github</a>
  </div>
</template>

<script>
export default {
  name: 'GoodNight',
  data () {
    return {
      text: `Good Night`
    }
  }
}
</script>

<style scoped>

.goodNight {
  color: rgb(18, 103, 177);
}
p {
  color: rgb(18, 103, 177);
}
</style>