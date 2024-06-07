<script setup lang="ts">
const emailAddress: string = "mailto:info@maxeffort.dev?subject=Remodeling Inquiry" + "_" + Date.now().toString();
</script>

<template>
    <div>
        <q-card class="my-card" dark>
            <q-img src="../assets/images/Logo_v2-NOBG.png">
                <div class="absolute-bottom">
                    <div class="text-subtitle2"></div>
                </div>
            </q-img>

            <q-card-actions>
                <q-btn flat href="tel:8478757196" icon="phone">Call Now</q-btn>
                <q-btn flat :href=emailAddress target="_blank">Email
                    Question</q-btn>
            </q-card-actions>
        </q-card>
    </div>
</template>

<style scoped></style>