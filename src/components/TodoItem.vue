<template>
    <div class="todo-item">
        <div class="todo-item-left">
                    <input type="checkbox" v-model="todo.completed">
                    <div v-if="!todo.editing" @dblclick="editTodo(todo)" class="todo-item-label" :class="{ completed : todo.completed }">{{ todo.title }}</div>
                    <input v-else class="todo-item-edit" type="text" v-model="todo.title" @blur="doneEdit(todo)" @keyup.enter="doneEdit(todo)" @keyup.esc="cancelEdit(todo)">
                </div>
                <div class="remove-item" @click="removeTodo(index)">
                    &times;
                </div>
            <div class="extra-container">
                <div><label><input type="checkbox" :checked="!anyRemaining" @change="checkAllTodos">Check All</label></div>
                <div>{{ remaining }} items left</div>
            </div>
            <div class="extra-container">
            <div>
                <button :class="{ active: filter == 'all' }" @click="filter = 'all'">All</button>
                <button :class="{ active: filter == 'active' }" @click="filter = 'active'">Active</button>
                <button :class="{ active: filter == 'completed' }" @click="filter = 'completed'">Completed</button>
            </div>
            </div>
    </div>
</template>

<script>
export default {
    name: 'todo-item',
}
</script>