<script setup lang="ts">
import PastWork from './PastWork.vue';
import services from '../data/ServiceData';
import whyData from '../data/WhyData';
import { ref } from 'vue';
import { contactVCF, emailLink, phoneLink } from '../data/misc';
import { useQuasar } from 'quasar';

const $q = useQuasar();
const slide = ref(services[1].title);

</script>

<template>
    <section>
        <PastWork class="work" />

    </section>
    <section id="about">
        <h3>Who We Are</h3>
        <h5>Trusted Company Who Delivers</h5>
        <p>
            A luxury home renovation is a significant investment, so why not choose the best? When you commit to such a
            project, you deserve more than just additional space or a new look. This is your chance to create the home
            you've always envisioned, complete with the most luxurious feel and the highest-quality features.
        </p>
        <p>
            Transform your house into the epitome of elegance and sophistication.
        </p>
        <p>In the Chicago area, B&B Remodeling stands unrivaled for luxury home renovation. Our award-winning team
            excels in transforming any space, from a single room to your entire property, into the home of your dreams.
            We specialize in top-of-the-line flooring, lighting, cabinetry, and more, turning the ordinary into the
            extraordinary. Whether you're looking to remodel your kitchen, bathroom, basement, or desire a complete home
            makeover, B&B Remodeling is the trusted name that delivers elegance, quality, and superior craftsmanship.

        </p>
    </section>
    <section>
        <h3>Why Choose Us?</h3>
        <h5>What Defines B&B</h5>
        <q-list>
            <q-item v-for="why in whyData" :key="why.index">
                <q-item-section>

                    <q-item-label align="left">
                        <strong>{{ why.title }}:</strong>
                    </q-item-label>
                    <q-item-label caption align="left" class="item-content">
                        {{ why.content }}
                    </q-item-label>
                </q-item-section>
            </q-item>
        </q-list>


    </section>
    <section id="service">
        <h3>Services</h3>
        <h5>Transform Your Home</h5>
        <p>With Expert Remodeling Services, B & B Remodeling will turn your house into the home of your dreams. With
            years of experience and a passion for perfection, our team of skilled professionals is dedicated to
            delivering top-quality remodeling services tailored to your unique vision and needs. Explore our
            comprehensive range of services below and discover how we can bring your remodeling dreams to life.
        </p>
        <q-carousel dark v-model="slide" transition-prev="slide-down" transition-next="slide-up" vertical animated
            arrows :autoplay="5500" infinite :height="$q.screen.width <= 512 ? '450px' : 'max-content'"
            class="service-carousel">

            <q-carousel-slide dark v-for="service in services  " :key=service.title :name=service.title bordered>
                <q-card class="service-card">
                    <q-card-section></q-card-section>
                    <q-card-section :horizontal="$q.screen.width >= 512">
                        <q-card-section class="text-h5 q-mt-sm q-mb-xs service-title">
                            {{ service.title }}
                        </q-card-section>
                        <q-separator :vertical="$q.screen.width >= 512" dark />
                        <q-card-section class="service-content">{{ service.content }}</q-card-section>
                    </q-card-section>
                    <q-card-section></q-card-section>
                </q-card>
            </q-carousel-slide>
        </q-carousel>

    </section>
    <section class="cta">
        <br />
        <p> </p>
    </section>

    <section id="contact">
        <h3>Contact Info</h3>
        <h5>Ready to start your remodeling journey?</h5>
        <p>Contact us today to schedule a consultation and take the first step toward transforming your home with B & B
            Remodeling.</p>
        <div class="contact-buttons">
            <q-btn flat size="lg" stack color="secondary" :href=emailLink target="_blank" class="contact-icon"
                icon="mail">
                Email
            </q-btn>
            <q-btn flat size="lg" stack color="secondary" :href=contactVCF class="contact-icon" icon="person"
                download>Save Our
                Info</q-btn>
            <q-btn flat size="lg" stack color="secondary" :href=phoneLink class="contact-icon" icon="phone"
                target="_blank">Call</q-btn>
        </div>
    </section>
</template>

<style scoped lang="scss">
section {
    /* border-top: 1.5px solid #DAA520; */
    /* border-bottom: 1px solid #eacc23; */
    min-width: 100%;
    font-size: 1rem;

}

.item-content {
    color: $accent;
}

.contact-buttons {
    display: flex;
    justify-content: space-around;
    align-items: center;
    flex-direction: row;
    flex-wrap: wrap;
}

.service-carousel {
    background-color: transparent;
    margin: auto auto;
    max-width: 800px;
    border-top: 1px solid $accent;
    border-bottom: 3px solid $accent;
    border-radius: 1rem;
}

.service-card--container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

.service-card {
    background-color: transparent;
    flex: 0 1 100%;
    max-width: 800px;
    color: $secondary;
    min-height: fit-content;
}

.service-title {
    font-weight: 800;
    color: $accent;

}

.service-content {
    font-weight: 300;
    color: $secondary;
    font-size: 1rem;
    line-height: 1.25;

}

section h5 {
    color: $accent;
    padding: 0 auto;
    margin-top: 0;
    margin-bottom: 0;
    border-bottom: 2px solid $secondary;
}

section h3 {
    margin-bottom: 0;
    padding-bottom: 0;
}

p {
    margin: 1rem auto;
}

.work {
    flex: 1 0 100%;
    padding: 0;
    margin: 0;

}

#contact {
    padding-bottom: 10rem;
    margin-bottom: 10rem;
}
</style>