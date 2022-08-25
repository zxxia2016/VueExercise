<template>
  <div class="list-group-item">
    <div class="handle">
      <a href="javascript:;" v-on:click="onBtnClick">删除</a>
    </div>
    <p class="user"><span>{{ comment.name }}</span><span>说:</span></p>
    <p class="centence">{{ comment.content }}</p>
  </div>
</template>

<script>
export default {
  props: {
    comment: Object,
    removeComment: Function,
    index: Number
  },
  data () {
    return {}
  },
  methods: { 
    onBtnClick () {
      const { comment, removeComment, index } = this
      const c = window.confirm(`Are you sure you want to remove this comment from ${comment.name}?`)
      if (c) {
        removeComment(index)
      }
    }
  }
}
</script>
<style>

li {
  transition: .5s;
  overflow: hidden;
}

.handle {
  width: 40px;
  border: 1px solid #ccc;
  background: #fff;
  position: absolute;
  right: 10px;
  top: 1px;
  text-align: center;
}

.handle a {
  display: block;
  text-decoration: none;
}

.list-group-item .centence {
  padding: 0px 50px;
}

.user {
  font-size: 22px;
}
</style>