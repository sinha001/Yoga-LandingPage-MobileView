<template>
  <Navbar />
  <HeroSection />
  <ExperienceCarousel />
  <AboutUs />
  <WhyChooseUs />
  <TestimonialSection />
  <UsableSection :title="CurriculumTitie" :tagline="CurrTagline" :stats="CurrStats" bgColor="#ffffff"
    statsColor="#FFF8F4" />
  <PhaseCard :phase="p1" :image="p1Image" :title="p1Title" :subtitle="p1Subtitle" :items="p1Items" />
  <PhaseCard2 :phase="p3" :title="p3Title" :items="p3Items" :columns="2" />
  <PhaseCard :phase="p2" :image="p2Image" :title="p2Title" :subtitle="p2Subtitle" :items="p2Items" />
  <DailySchedule/>
  <WhatIncluded/>
  <ApplicationProcess/>
  <PricingPackages/>
  <EnrollSection />
  <GurusSection/>
  <LineageTimeline />
  <ReviewSection/>
  <GallerySection/>
  <UsableSection :title="title" :tagline="tagline" :stats="stats" />
  <SuccessSection2 />
  <ContactUs />
  <FAQSection />
  <Footer />
</template>

<script setup>
import Navbar from './components/Navbar.vue'
import HeroSection from './components/Hero-Section.vue';
import ExperienceCarousel from './components/ExperienceCarousel.vue';
import AboutUs from './components/AboutUs.vue';
import WhyChooseUs from './components/WhyChooseUs.vue';
import TestimonialSection from './components/TestimonialSection.vue';
import Footer from './components/Footer.vue';
import ContactUs from './components/ContactUs.vue';
import FAQSection from './components/FAQSection.vue';
import SuccessSection2 from './components/SuccessSection2.vue';
import UsableSection from './components/UsableSection.vue';
import LineageTimeline from './components/LineageTimeline.vue';
import EnrollSection from './components/EnrollSection.vue';
import PhaseCard from './components/PhaseCard.vue';
import PhaseCard2 from './components/PhaseCard2.vue';
import DailySchedule from './components/DailySchedule.vue';
import WhatIncluded from './components/WhatIncluded.vue';
import ApplicationProcess from './components/ApplicationProcess.vue';
import PricingPackages from './components/PricingPackages.vue';
import GurusSection from './components/GurusSection.vue';
import ReviewSection from './components/ReviewSection.vue';

import { ref } from "vue";
import GallerySection from './components/GallerySection.vue';


const title = ref("Where Our <br> Graduates Are Now");
const tagline = ref("SUCCESS STORIES");

const stats = ref([
  { number: "85%", text: "Of Graduates Teach Yoga Internationally" },
  { number: "50+", text: "Countries’ Alumni Worldwide" },
  { number: "100+", text: "Yoga Studios & Retreats Started By Our Students" },
  { number: "100+", text: "Yoga Studios & Retreats Started By Our Students" }
]);

const CurriculumTitie = ref("How Is Your Yoga <br> Journey Structured?");
const CurrTagline = ref("CURRICULUM");

const CurrStats = ref([
  { number: "27", text: "Days of Training" },
  { number: "10+", text: "Expert Teachers" },
  { number: "200+", text: "Hours Of Learning" },
  { number: "Yoga Alliance", text: "Certification" }
]);

const p1 = ref("PHASE 1");
const p1Image = ref(new URL('./assets/Images/Rectangle 6819.png', import.meta.url).href);
const p1Title = ref("Traditional Fire Ceremony & Yogic Introduction");
const p1Subtitle = ref("Fire Ceremony & Yogic Initiation");

const p1Items = ref([
  'Traditional Vedic Fire Ceremony to begin your transformational journey',
  'Introduction to Ashram life, yogic discipline, and daily routines',
  'Guided breathwork & meditation to set intentions for the journey'
]);

const p2 = ref("PHASE 3");
const p2Image = ref(new URL('./assets/Images/Rectangle 6819.png', import.meta.url).href);
const p2Title = ref("Graduation & Your Future As a Yoga Teacher");
const p2Subtitle = ref("Become a Globally Certified Yoga Instructor");

const p2Items = ref([
  'Official Yoga Alliance Certification to teach worldwide',
  'Career guidance: start your own yoga school or join top retreats',
  'Join our elite alumni network & lifetime mentorship'
]);


const p3 = ref("PHASE 2");
const p3Title = ref("Deep-Dive Into Yoga Studies");

const p3Items = ref([
  "Hatha Yoga",
  "Kundalini Yoga",
  "Satkarma",
  "Mudra — Gesture",
  "Yogic Relaxation Techniques",
  "Teaching Methodology",
  "Mantra Chanting",
  "Himalayan Excursion",
  "Certification Ceremony",
  "Ashtanga Vinyasa",
  "Pranayama",
  "Bandhas",
  "Meditation",
  "Alignment, Correction & Adjustment",
  "Yoga Philosophy",
  "Bhajan Or Spiritual Songs",
  "Cultural Program"
]);
</script>

<style scoped></style>
