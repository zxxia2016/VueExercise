<template>
    <div class="todo-header">
        <input type="text" placeholder="请输入你的任务名称，按回车键确认" 
        v-model="title"
        @keyup.enter="onBtnEnter"/>
    </div>
</template>
<script>
export default {
  props: {
    AddTodoItem: Function   
  },
  data () {
    return {
      title: ''
    }
  },
  methods: {
    onBtnEnter () {
      if (window.confirm('confirm add todo ?')) {
        this.AddTodoItem(this.title)
      }
    }
  }
}
</script>
<style>

/*让div内部文字居中*/
.todo-header {
    text-align: center;
}
/* border 和 outline 相似， outline 不占据空间，绘制于元素内容周围。*/
.todo-header input {
    width: 560px;
    height: 28px;
    font-size: 14px;
    border: 1px solid #ccc;
    border-radius: 4px;
    padding:4px 7px;
}
/* :focus 当用户点击或触摸元素或通过键盘的 “tab” 键选择它时会被触发。 */
.todo-header input:focus {
    outline: none;
    /* outline: solid; */
    border-color: rgba(82, 168, 236, 0.8);
    box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075),
        0 0 8px rgba(82, 168, 236, 0.6);
}
</style>