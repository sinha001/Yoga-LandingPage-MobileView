<template>
    <div class="container why-choose-us">
        <h2 class="choose-section-title">Why Our Students <br /> Choose Us?</h2>

        <div class="carousel-container">
            <div class="carousel-track" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
                <div class="carousel-card" v-for="(card, index) in cards" :key="index">
                    <div class="card-icon">
                        <img :src="card.icon" alt="icon" />
                    </div>
                    <h3 class="card-title">{{ card.title }}</h3>
                    <div class="card-content">
                        <div v-for="(point, i) in card.points" :key="i" class="card-point">
                            <span class="check-icon">✔</span>
                            <div>
                                <h4 class="content-head">{{ point.heading }}</h4>
                                <p class="content-text">{{ point.text }}</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Carousel Dots -->
            <div class="carousel-dots">
                <span 
                    v-for="(card, index) in cards" 
                    :key="'dot-' + index"
                    :class="{ active: currentIndex === index }"
                    @click="goToSlide(index)">
                </span>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const currentIndex = ref(0);
const cards = ref([
    {
        icon: new URL('../assets/Images/iconoir_yoga.png', import.meta.url).href,
        title: 'Quality Education & Structured Learning',
        points: [
            { heading: 'Deep, Comprehensive Yoga Training', text: 'A well-structured curriculum that blends traditional yogic wisdom with modern methodologies to create confident and knowledgeable teachers.' },
            { heading: 'Hands-On, Experiential Learning', text: 'Focus on practical teaching experience, alignment corrections, and real-world applications - ensuring you are truly ready to teach.' }
        ]
    },
    {
        icon: new URL('../assets/Images/hugeicons_school.png', import.meta.url).href,
        title: 'A School That Feels Like Home',
        points: [
            { heading: 'A Close-Knot, Supportive Community', text: "Our school isn't just a place to learn-it's a family where every students is valued, mentored, and guided throughout their journey." },
            { heading: 'Safe, Nurturing, and Inclusive Space', text: 'A stress-free environment where you can focus fully on your practise, growth, and inner transformation.' }
        ]
    },
    {
        icon: new URL('../assets/Images/hugeicons_yoga-03 (1).png', import.meta.url).href,
        title: 'A Life-Changing Yoga Experience',
        points: [
            { heading: 'More Than a Course - A Transformational Journey', text: "Beyond physical postures, you'll develop self-awareness, mindfulness, and a deeper connection to your practise." },
            { heading: 'Immersed in the Spiritual Energy of Rishikesh', text: 'Experience yoga in its birthplace, surrounded by sacred temples, the Ganges, and the wisdom of ancient yogis.' }
        ]
    }
]);

const goToSlide = (index) => {
    currentIndex.value = index;
};
</script>

<style scoped>
.why-choose-us {
    text-align: center;
    padding: 50px 20px;
    background: #FFF7F0;
}

.choose-section-title {
    font-size: 28px;
    color: #734875;
    margin-bottom: 20px;
}

/* Carousel */
.carousel-container {
    position: relative;
    overflow: hidden;
    width: 100%;
    max-width: 800px;
    margin: auto;
}

.carousel-track {
    display: flex;
    transition: transform 0.5s ease-in-out;
}

.carousel-card {
    flex: 0 0 100%;
    background: white;
    border: 1px solid #F4D4A7;
    border-radius: 14px;
    padding: 20px;
    text-align: left;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

.card-icon img {
    width: 50px;
    height: 50px;
    background: #FFF2E0;
    padding: 10px;
    border-radius: 11px;
}

.card-title {
    font-size: 20px;
    color: #2C2C2C;
    font-weight: 500;
    margin: 15px 0;
}

.card-content {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 32px;
}

.content-head
{
    font-size: 14px;
    font-family: 500;
}

.content-text{
    font-size: 12px;
    font-weight: 400;
}
.card-point {
    display: flex;
    align-items: flex-start;
    gap: 10px;
}

.check-icon {
    color: #734875;
    font-size: 16px;
}

/* Dots */
.carousel-dots {
    display: flex;
    justify-content: center;
    margin-top: 15px;
}

.carousel-dots span {
    width: 12px;
    height: 12px;
    background: #F4D4A7;
    border-radius: 50%;
    margin: 0 5px;
    cursor: pointer;
    transition: all 0.3s ease;
}

.carousel-dots .active {
    background: #FF5E14;
    width: 20px;
    border-radius: 8px;
}
</style>
