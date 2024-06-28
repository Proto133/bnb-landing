<script setup lang="ts">
import { Ref, ref } from 'vue';
import { emailLink } from '../data/misc';
// const emailAddress: string = "mailto:info@maxeffort.dev?subject=Remodeling Inquiry" + "_" + Date.now().toString();
const slide: Ref = ref(1);
const autoplay: Ref = ref(true);
</script>

<template>
    <q-card flat dark>
        <q-carousel animated v-model="slide" infinite :autoplay="autoplay" transition-duration="30"
            transition-prev="fade" transition-next="fade" @mouseenter="autoplay = false" @mouseleave="autoplay = true">
            <q-carousel-slide :name="1" img-src="../assets/images/white_marble_bath_tile.png" />
            <q-carousel-slide :name="2" img-src="../assets/images/intricate_tile_shower.png" />
            <q-carousel-slide :name="3" img-src="../assets/images/tile_shower_base.png" />
            <q-carousel-slide :name="4" img-src="https://cdn.quasar.dev/img/quasar.jpg" />
        </q-carousel>
        <q-space />
        <q-card-actions align="evenly">
            <q-btn flat color="secondary" :href=emailLink target="_blank" icon="mail">
                Email
            </q-btn>
            <q-btn flat color="secondary" href="tel:18478757196" icon="phone" target="_blank">Call</q-btn>
        </q-card-actions>
    </q-card>
</template>