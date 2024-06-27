<script setup lang="ts">
import { watchEffect } from 'vue';
import Content from './components/Content.vue'
import { useQuasar } from 'quasar';

const emailAddress: string = "mailto:info@maxeffort.dev?subject=Remodeling Inquiry" + "_" + Date.now().toString();
const year = new Date().getFullYear();
const $q = useQuasar();

let justification: string = "justify-between"

$q.screen.setSizes({ sm: 300, md: 500, lg: 1000, xl: 2000 })
watchEffect(() => {
  justification = $q.screen.lt.md ? "justify-center" : "justify-between";
  console.log(justification)
})

</script>

<template id="app">
  <q-layout view="hHh lpR fFf">

    <q-header>
      <q-toolbar v-if="$q.screen.lt.sm == false" class="justify-center">
        <q-img class="badge" src="./assets/images/Logo_v2-NOBG.png" />

      </q-toolbar>
      <q-toolbar class="fit row wrap" :class=justification>
        <q-tabs class="wrap" stretch>
          <q-route-tab to="#about" label="About" />
          <q-route-tab to="#service" label="Service" />
          <q-route-tab to="/page3" label="Contact" />
        </q-tabs>
        <!-- <q-space v-if="$q.screen.lt.md" /> -->
        <q-toolbar v-if="$q.screen.gt.sm" inset class="justify-end">

          <q-tabs stretch>
            <q-route-tab flat color=" secondary" :href=emailAddress target="_blank" icon="mail">
              Email
            </q-route-tab>
            <q-route-tab flat color="secondary" href="tel:18478757196" icon="phone" target="_blank">Call</q-route-tab>
          </q-tabs>
        </q-toolbar>
      </q-toolbar>
      <q-toolbar v-if="$q.screen.lt.md" class="justify-center">

        <q-tabs stretch>
          <q-route-tab flat color=" secondary" :href=emailAddress target="_blank" icon="mail">
            Email
          </q-route-tab>
          <q-route-tab flat color="secondary" href="tel:18478757196" icon="phone" target="_blank">Call</q-route-tab>
        </q-tabs>
      </q-toolbar>



    </q-header>
    <q-space />
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

.logo-div {

  justify-content: center;
}

.badge {
  flex: 0 1 33%;
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
  justify-content: space-evenly;
}

.split {
  flex: 1 0 100%;
}
</style>