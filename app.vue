<script lang="ts" setup>
import store from "./store/store";

const _store = store();
</script>

<template>
  <v-app :theme="_store.theme">
    <v-main>
      <v-container class="pa-5 pa-sm-10 pa-md-15">
        <NuxtLayout>
          <NuxtPage />
        </NuxtLayout>
      </v-container>
    </v-main>
  </v-app>
</template>
