<script lang="ts" setup>
import store from "~/store/store";
import logo from "~/public/favicon.ico";

const _store = store();
</script>

<template>
  <v-app-bar class="px-5 px-sm-15">
    <template v-slot:prepend>
      <div class="logo d-flex justify-center align-center ga-2">
        <v-img :src="logo" width="30" />
        <span class="text-subtitle-1 text-uppercase font-weight-bold text-sm-h5"
          >DragDrop</span
        >
      </div>
    </template>
    <template v-slot:append>
      <div class="d-flex justify-center align-center ga-2">
        <v-btn
          @click="_store.changeTheme"
          :icon="_store.theme === 'light' ? 'mdi-weather-night' : 'mdi-weather-sunny'"
        />
      </div>
    </template>
  </v-app-bar>
</template>

<style scoped></style>
