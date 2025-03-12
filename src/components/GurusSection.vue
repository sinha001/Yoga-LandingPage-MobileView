<template>
    <div class="gurus-section">
        <p class="section-highlight">MEET YOUR GURUS’</p>
        <h2 class="section-title">Train with the Best Yoga Masters</h2>
        <p class="section-subtitle">
            Learn from certified yoga masters dedicated to guiding you on your journey to balance, strength, and mindfulness.
        </p>

        <!-- ✅ Gurus Grid -->
        <div class="gurus-grid">
            <div class="guru-card" v-for="(guru, index) in gurus" :key="index">
                <!-- ✅ Background Image Fills Entire Card -->
                <div class="guru-image" :style="{ backgroundImage: `url(${guru.image})` }">
                    <div class="play-button">
                        <img src="../assets/yogi-image/play-button.png" alt="Play" />
                    </div>
                    <div class="guru-info">
                        <h3 class="guru-name">{{ guru.name }}</h3>
                        <p class="guru-title">{{ guru.title }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>

import { ref } from "vue";

const gurus = ref([
    { name: "Yogi Pramod Sahu", title: "DIRECTOR", image: new URL("../assets/yogi-image/image-3.png" , import.meta.url).href },
    { name: "Yogi Kusagra", title: "KUNDALINI", image: new URL("../assets/yogi-image/image-4.png" , import.meta.url).href },
    { name: "Yogi Lakhi Ram", title: "MEDITATION, PRANAYAMA", image: new URL("../assets/yogi-image/image-5.png" , import.meta.url).href },
    { name: "Yogini Pooja", title: "HIMALAYAN YOGA", image: new URL("../assets/yogi-image/image-3.png" , import.meta.url).href },
    { name: "Yogi Abhishek Negi", title: "ASHTANGA VINYASA ADV.", image: new URL("../assets/yogi-image/image-4.png" , import.meta.url).href },
    { name: "Ankit Ranakoti", title: "HATHA YOGA", image: new URL("../assets/yogi-image/image-5.png" , import.meta.url).href }
]);
</script>


<style scoped>
.gurus-section {
    padding: 48px 24px;
    background-color: #FFF8F4;
    text-align: center;
}

/* ✅ Section Header */
.section-highlight {
    color: #FF6600;
    font-size: 12px;
    font-weight: 400;
    letter-spacing: 1px;
}

.section-title {
    font-size: 36px;
    color: #4F2553;
    font-weight: 400;
    letter-spacing: 0;
    margin-bottom: 8px;
}

.section-subtitle {
    font-size: 16px;
    color: #455A64;
    letter-spacing: 0;
    font-family: 0;
    margin-bottom: 24px;
}

/* ✅ Gurus Grid Layout */
.gurus-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
}

.guru-card {
    position: relative;
    overflow: hidden;
    border-radius: 12px;
    height: 100%; /* Changed from fixed 300px to flexible */
    min-height: 280px; /* Ensures the card does not shrink */
}

/* ✅ Ensure Background Image Covers the Entire Card */
.guru-image {
    width: 100%;
    height: 100%;
    min-height: 280px; /* Prevents collapse */
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat; /* Fix for missing images */
    border-radius: 12px;
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
}

/* ✅ Fix for Play Button Overlay */
.play-button {
    position: absolute;
    top: 12px;
    right: 12px;
    border-radius: 50%;
    width:40px;
    height:40px;
    padding: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1; /* Ensures it appears on top */
}

/* ✅ Fix for Guru Info Text */
.guru-info {
    width: 100%;
    padding: 12px;
    color: white;
    background: linear-gradient(to top, rgba(0, 0, 0, 0.6), transparent);
    position: absolute;
    bottom: 0;
    left: 0;
    text-align: start;

}



.play-button img {
    width: 24px;
    height: 24px;
}



.guru-name {
    font-size: 20px;
    font-weight: 400;
    letter-spacing: 0;
}

.guru-title {
    font-size: 10px;
    font-weight: 400;
    letter-spacing: 1px;
    text-transform: uppercase;
}

</style>

