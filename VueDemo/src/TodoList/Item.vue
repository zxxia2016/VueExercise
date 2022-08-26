<template>
    <li>
        <!-- Label当用户选择该标签时，浏览器就会自动将焦点转到和标签相关的表单控件上 -->
        <label>
            <input type="checkbox" v-model="item.finished" />
            <span>&nbsp;{{item.title}}</span>
        </label>
        <button class="btn btn-danger" style="display:none">删除</button>
    </li>
</template>
<script>
export default {
  props: {
    item: Object
  }
}
</script>
<style>

/*item*/
li {
    list-style: none;
    height: 36px;
    line-height: 36px;
    padding: 0 5px;
    border-bottom: 1px solid #ddd;
}

li label {
    /* float: left; */
    cursor: pointer;
}

li label li input {
    vertical-align: middle;
    margin-right: 6px;
    position: relative;
    top: -1px;
}

li button {
    float: right;
    display: none;
    margin-top: 3px;
}

li:before {
    content: initial;
}

li:last-child {
    border-bottom: none;
}
</style>