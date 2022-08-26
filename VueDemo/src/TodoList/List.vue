<template>
    <div>
        <ul class="todo-main">
            <Item v-for="(item, index) in list" :key="index" :item="item"/>
        </ul>
    </div>
</template>
<script>
import Item from './Item.vue'
export default {
  props: {
    list: Array
  },
  components: {
    Item
  }
}
</script>
<style>

/*main*/
.todo-main {
    margin-left: 0px;
    margin-top: 10px;
    border: 1px solid #ddd;
    border-radius: 2px;
    padding: 0px;
}

.todo-empty {
    height: 40px;
    line-height: 40px;
    border: 1px solid #ddd;
    border-radius: 2px;
    padding-left: 5px;
    margin-top: 10px;
}
</style>