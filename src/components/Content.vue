<script setup lang="ts">
import PastWork from './PastWork.vue';

const emailAddress: string = "mailto:info@maxeffort.dev?subject=Remodeling Inquiry" + "_" + Date.now().toString();
</script>

<template>
    <section>
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
    <section id="about">
        <h1>About</h1>
        <p>I am a full-stack web developer with a passion for creating intuitive, responsive, and user-friendly web
            applications. I have a background in computer science, and I am currently pursuing a Bachelor's of Science
            in Computer Science at the University of Maryland, College Park.</p>
    </section>
    <section id="service">
        <h1>Service</h1>
        <p>I am a full-stack web developer with a passion for creating intuitive, responsive, and user-friendly web
            applications. I have a background in computer science, and I am currently pursuing a Bachelor's of Science
            in Computer Science at the University of Maryland, College Park.</p>
    </section>
</template>

<style scoped>
section {
    /* border-top: 1.5px solid #DAA520; */
    border-bottom: 1px solid #eacc23;
    min-width: 80%;
    font-size: 1rem;

}
</style>