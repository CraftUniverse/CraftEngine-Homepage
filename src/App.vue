<template>
  <v-app>
    <v-main>
      <router-view />
      <v-footer app :elevation="16">
        <v-row justify="center" no-gutters>
          <v-btn
            v-for="link in links"
            :key="link.title"
            class="mx-2"
            color="white"
            rounded="xl"
            variant="text"
            :to="link.url.startsWith('https://') ? '' : link.url"
            :href="link.url.startsWith('https://') ? link.url : ''"
            :target="link.url.startsWith('https://') ? '_blank' : '_self'"
          >
            {{ link.title }}
          </v-btn>
          <v-col class="text-center mt-4" cols="12">
            &#169; {{ new Date().getFullYear() }} —
            <strong>CraftUniverse</strong>
          </v-col>
        </v-row>
      </v-footer>
    </v-main>
  </v-app>
</template>

<script lang="ts" setup>
//@ts-ignore
import { ref } from "vue";

const links = ref<{ title: string; url: string }[]>([
  { title: "Home", url: "/" },
  { title: "Discord", url: "https://rcurl.de/cudc" },
  { title: "Github", url: "https://github.com/CraftUniverse" },
]);
</script>
