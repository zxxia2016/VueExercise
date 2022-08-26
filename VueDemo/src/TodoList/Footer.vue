<template>
    <div class="todo-footer">
        <label>
            <input type="checkbox" v-model="checkAllFinished"/>
        </label>
        <span>
            已完成{{finishedCount}}/全部{{list.length}}
        </span>
        <button class="btn btn-danger" @click="onBtnClick">清除已完成任务</button>
    </div>
</template>
<script>
export default {
  props: {
    list: Array,
    selectAll: Function,
    removeFinishedItems: Function
  },
  computed: {
    finishedCount () {
      let count = 0
      for (let i = 0; i < this.list.length; i++) {
        const item = this.list[i]
        if (item.finished) {
          count++
        }
      }
      return count
    },
    checkAllFinished: {
      get () {
        return this.finishedCount === this.list.length && this.finishedCount > 0
      },
      set (value) {
        this.selectAll(value)
      }
    }
    
  },
  methods: {
    onBtnClick () {
      this.removeFinishedItems()
    }
  }
}
</script>
<style>

/*footer*/
.todo-footer {
    height: 40px;
    line-height: 40px;
    padding-left: 6px;
    margin-top: 5px;
}

.todo-footer label {
    display: inline-block;
    margin-right: 20px;
    cursor: pointer;
}

.todo-footer label input {
    position: relative;
    top: -1px;
    vertical-align: middle;
    margin-right: 5px;
}

/* 只能选择一层button */
.todo-footer button {
    float: right;
    margin-top: 5px;
}

</style>