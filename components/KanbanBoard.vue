<script lang="ts" setup>
import { useDragAndDrop } from "@formkit/drag-and-drop/vue";

const todoItems = [
  "Schedule perm",
  "Rewind VHS tapes",
  "Make change for the arcade",
  "Get disposable camera developed",
  "Learn C++",
  "Return Nintendo Power Glove",
];
const doneItems = ["Pickup new mix-tape from Beth"];

const [todoList, todos] = useDragAndDrop(todoItems, {
  group: "todoList",
  sortable: false,
});
const [doneList, dones] = useDragAndDrop(doneItems, {
  group: "todoList",
  sortable: false,
});
</script>

<template>
  <v-row class="kanban-board d-flex">
    <v-col cols="12" sm="12" md="6">
      <v-card class="card d-flex flex-column ga-2 pa-3 rounded-lg" min-height="500">
        <v-card-title>Todo List</v-card-title>
        <hr />
        <v-list ref="todoList" class="w-100">
          <v-list-item
            v-for="todo in todos"
            :key="todo"
            class="cursor-pointer pa-3 bg-amber-darken-1 my-3 rounded-lg"
          >
            {{ todo }}
          </v-list-item>
        </v-list>
      </v-card>
    </v-col>

    <v-col cols="12" sm="12" md="6">
      <v-card class="card d-flex flex-column ga-2 pa-3 rounded-lg" min-height="500">
        <v-card-title>Done List</v-card-title>
        <hr />
        <v-list ref="doneList" class="w-100">
          <v-list-item
            v-for="done in dones"
            :key="done"
            class="cursor-pointer pa-3 bg-teal-darken-1 my-3 rounded-lg"
            >{{ done }}</v-list-item
          >
        </v-list>
      </v-card>
    </v-col>
  </v-row>
</template>

<style scoped>
.form {
  background-color: #586881;
}
.drop-box {
  border: 3px dashed;
}
</style>
