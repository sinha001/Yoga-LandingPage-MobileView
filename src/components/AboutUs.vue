<template>
    <div class="container about-us mt-5">
        <div class="row">
            <div class="Frame-1039">
                <h5 class="frame-1039-about">ABOUT US</h5>
                <h3 class="frame-1039-ques">What Makes Us the<br /> #1 Yoga School in the World?</h3>
            </div>
            <p class="frame-1039-para">
                Our Yoga Teacher Training program is designed for those who seek authentic, in-depth knowledge of yoga in its birthplace, Rishikesh. Over the course of your training, you'll immerse yourself in ancient practices, learn from world-class teachers, and become part of an elite global yoga network.
            </p>
        </div>
        <div class="row">
            <AboutCardSection :cards="cardData" />
        </div>
        <div class="row mt-0 d-flex justify-content-center align-items-center">
            <button class="btn-about-us">Apply Now & Join the Elite</button>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import AboutCardSection from './AboutCardSection.vue';

const cardData = ref([
    {
        image: new URL('../assets/Images/Rectangle 6880.png', import.meta.url).href,
        title: 'Unmatched',
        subtitle: 'Learning & Lineage',
        items: [
            { title: 'World-Class Faculty & Ancient Teachings', description: 'Train under renowned yoga masters with decades of expertise in Hatha, Ashtanga, Kundalini, and more. Our school follows a direct lineage from ancient yogic traditions.' },
            { title: 'Authentic & Traditional Yogic Practices', description: 'Experience yoga in its purest form, integrating philosophy, medication, and spiritual wisdom passed down for generations.' },
            { title: 'Personalized Learning Experience', description: 'Small batch sizes ensure one-on-one guidance, personalized corrections, and direct mentorship from senior instructors.' }
        ]
    },
    {
        image: new URL('../assets/Images/Rectangle 6880 (1).png', import.meta.url).href,
        title: 'Premium Experience &',
        subtitle: 'Serene Lifestyle',
        items: [
            { title: 'Luxury Stay & Holistic Living', description: 'Live in a peaceful, fully equipped ashram with private & shared accommodations, an on-site yoga hall, and meditation spaces.' },
            { title: 'Nutritious Organic Vegetarian Meals', description: 'Enjoy sattvic, plant-based meals designed to nourish both body and mind, enhancing your yoga journey.' },
            { title: 'Daily Rituals & Transformative Excursions', description: 'Participate in fire ceremonies, sunrise meditations by the Ganges, and guided visits to sacred Himalayan temples.' }
        ]
    },
    {
        image: new URL('../assets/Images/Rectangle 6880 (2).png', import.meta.url).href,
        title: 'Global Certification &',
        subtitle: 'Career Success',
        items: [
            { title: 'Global Yoga Alliance Certification', description: 'Graduate as a certified yoga teacher, recognized worldwide, and be eligible to teach at studios, retreats, and wellness centers globally.' },
            { title: 'Elite Alumni Network & Career Support', description: 'Join a global community of yoga instructors, access career guidance, and explore teaching opportunities worldwide.' },
            { title: 'Start Your Own Yoga School', description: 'Empower yourself to teach yoga anywhere or build your own yoga retreat with the business knowledge we provide.' }
        ]
    }
]);
</script>

<style scoped>
.about-us {
    padding: 48px 24px;
}

.frame-1039-about {
    font-size: 14px;
    color: #FF5E14;
    letter-spacing: 1px;
}

.frame-1039-ques {
    margin-top: 10px;
    font-size: 32px;
    color: #734875;
    line-height: 1.3;
}

.frame-1039-para {
    margin-top: 24px;
    font-size: 16px;
    color: #455A64;
    text-align: start;
    line-height: 1.6;
    letter-spacing: 0;
}

.btn-about-us
{
    width: 260px;
    height: 48px;
    background-color: #FF5E14;
    color: white;
    border-radius: 13px;
    border: none;
    font-size: 0.9rem;
    font-weight: 600;
}
</style>
