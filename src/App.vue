<script setup lang="ts">
import Content from './components/Content.vue'
import PastWork from './components/PastWork.vue'
import { ref } from 'vue';
// const rightDrawerOpen = ref(false);
const year = new Date().getFullYear();

// const toggleRightDrawer = () => {
//   rightDrawerOpen.value = !rightDrawerOpen.value;
// }


</script>

<template id="app">
  <q-layout view="hHh lpR fFf">
    <!-- <q-button :onclick="toggleRightDrawer">
      Drawer
    </q-button> 
     <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
      drawer content
    </q-drawer> -->
    <!-- <q-header elevated> -->

    <q-toolbar>

      <q-img class="badge" src="./assets/images/Logo_v2-NOBG.png" />
      <h3>

        B & B Remodeling
      </h3>

      <q-space />

      <q-tabs shrink stretch>
        <q-route-tab to="#about" label="About" />
        <q-route-tab to="#service" label="Service" />
        <q-route-tab to="/page3" label="Contact" />
      </q-tabs>
    </q-toolbar>

    <!-- </q-header> -->

    <q-page-container id="page">

      <Content class="split" />
      <!-- <PastWork class="split work" /> -->
    </q-page-container>

    <q-footer elevated class="bg-grey-8 text-white">
      <div id="Footer">
        <p>
          All rights reserved. Copyright &copy; {{ year }} B&B Bath LLC
        </p>
      </div>
    </q-footer>

  </q-layout>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.badge {
  width: 7rem;
  height: 7rem;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

#page {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.split {
  flex: 1 0 100%;
  margin: 1rem;
}

.work {
  min-width: 400px;
}
</style>