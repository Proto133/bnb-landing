<script setup lang="ts">
import PastWork from './PastWork.vue';
import services from '../data/ServiceData';
import { ref } from 'vue';
const slide = ref(services[1].title);

</script>

<template>
    <section>
        <PastWork class="work" />

    </section>
    <section id="about">
        <h3>Who We Are</h3>
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
    <section id="services">
        <h3>Services</h3>
        <h5>Transform Your Home</h5>
        <p>With Expert Remodeling Services, B & B Remodeling will turn your house into the home of your dreams. With
            years of experience and a passion for perfection, our team of skilled professionals is dedicated to
            delivering top-quality remodeling services tailored to your unique vision and needs. Explore our
            comprehensive range of services below and discover how we can bring your remodeling dreams to life.
        </p>
        <q-carousel dark v-model="slide" transition-prev="slide-down" transition-next="slide-up" vertical animated
            arrows :autoplay="5500" infinite height="250px">

            <q-carousel-slide dark v-for="service in   services  " :key=service.title :name=service.title bordered>
                <q-card class="service-card">
                    <q-card-section></q-card-section>
                    <q-card-section horizontal>
                        <q-card-section class="text-h5 q-mt-sm q-mb-xs">
                            {{ service.title }}
                        </q-card-section>
                        <q-separator vertical dark />
                        <q-card-section>{{ service.content }}</q-card-section>
                    </q-card-section>
                    <q-card-section></q-card-section>
                </q-card>
            </q-carousel-slide>
        </q-carousel>

    </section>
    <section>
        <h4>Why Choose Us?</h4>
        <q-list>
            <q-item>
                <q-item-section>
                    <strong>Experienced Professionals:</strong>
                </q-item-section>
                <q-item-section align="left">
                    Our team of licensed and insured experts brings years of
                    experience to every project, ensuring top-notch craftsmanship and attention to detail.
                </q-item-section>
            </q-item>



            <q-item>
                <q-item-section> <strong>Customer-Centric Approach:</strong> </q-item-section>
                <q-item-section>

                    We listen to your needs
                    and work closely with you
                    throughout
                    the remodeling process to ensure your complete satisfaction.
                </q-item-section>
            </q-item>
            <q-item>
                <q-item-section> <strong>Quality Materials:</strong> </q-item-section>
                <q-item-section>We use only the highest quality
                    materials and the latest
                    techniques
                    to deliver durable, long-lasting results.</q-item-section></q-item>
            <q-item>
                <q-item-section> <strong>Transparent Pricing:</strong></q-item-section>
                <q-item-section> No hidden fees or surprises. We
                    provide clear, detailed quotes
                    and
                    work within your budget to achieve your desired outcome.</q-item-section></q-item>
            <q-item>
                <q-item-section><strong>Timely Completion:</strong></q-item-section> <q-item-section>We understand the
                    importance of
                    your time and strive to complete
                    all
                    projects on schedule, with minimal disruption to your daily life.</q-item-section></q-item>

        </q-list>

        <p>Ready to start your remodeling journey? <a href="contact.html">Contact us today</a> to schedule a
            consultation and take the first step toward transforming your home with B & B Remodeling.</p>
    </section>

    <section id="contact">
        <h3>Contact Info</h3>
        <p>This is our contact info</p>
    </section>
</template>

<style scoped lang="scss">
section {
    /* border-top: 1.5px solid #DAA520; */
    /* border-bottom: 1px solid #eacc23; */
    min-width: 80%;
    font-size: 1rem;

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
    color: $secondary
}

.work {
    width: 100vw;
    padding: 0;
    margin: 0;
}
</style>