<template>
  <div class="container">
    <img alt="Vue logo" src="../assets/logo.png" class="logo">
    <to-do-list></to-do-list>
  </div>
</template>

<script>
// @ is an alias to /src
import TodoList from '@/components/TodoList.vue'

export default {
  components: {
    'to-do-list': TodoList
  }
}
</script>
