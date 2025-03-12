<template>
    <div class="reviews-section">
        <p class="section-highlight">FEEDBACK & REVIEWS</p>
        <h2 class="section-title">What Our Student Says About Us</h2>
        <p class="section-subtitle">
            Real stories from our yoga community. See how our classes have transformed lives!
        </p>

        <!-- ✅ Scrollable Cards Container -->
        <div class="reviews-wrapper" ref="scrollContainer">
            <div 
                class="review-card"
                v-for="(review, index) in reviews"
                :key="index"
                :style="{ backgroundImage: `url(${review.image})` }"
            >
                <div class="play-button">
                    <img src="../assets/yogi-image/play-button.png" alt="Play" />
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

const reviews = ref([
    { image: new URL("../assets/yogi-image/Frame 1150.png", import.meta.url).href },
    { image: new URL("../assets/yogi-image/Frame 1151.png", import.meta.url).href },
    { image: new URL("../assets/yogi-image/Frame 1150.png", import.meta.url).href },
    { image: new URL("../assets/yogi-image/Frame 1151.png", import.meta.url).href }
]);

const scrollContainer = ref(null);

const enableDragScroll = () => {
    const container = scrollContainer.value;
    let isDown = false;
    let startX;
    let scrollLeft;

    container.addEventListener("mousedown", (e) => {
        isDown = true;
        startX = e.pageX - container.offsetLeft;
        scrollLeft = container.scrollLeft;
        container.style.cursor = "grabbing";
    });

    container.addEventListener("mouseleave", () => {
        isDown = false;
        container.style.cursor = "grab";
    });

    container.addEventListener("mouseup", () => {
        isDown = false;
        container.style.cursor = "grab";
    });

    container.addEventListener("mousemove", (e) => {
        if (!isDown) return;
        e.preventDefault();
        const x = e.pageX - container.offsetLeft;
        const walk = (x - startX) * 2; // Scroll speed factor
        container.scrollLeft = scrollLeft - walk;
    });
};

onMounted(() => {
    enableDragScroll();
});
</script>

<style scoped>
.reviews-section {
    padding: 48px 24px;
    background-color: #FFF8F4;
    text-align: start;
}

/* ✅ Section Header */
.section-highlight {
    color: #FF6600;
    font-size: 14px;
    font-weight: 400;
    letter-spacing: 1px;
}

.section-title {
    font-size: 36px;
    color: #4F2553;
    font-weight: 400;
    letter-spacing: -2px;
    margin-bottom: 8px;
}

.section-subtitle {
    font-size: 16px;
    font-family: 400;
    letter-spacing: 0;
    color: #455A64;
    margin-bottom: 24px;
}

/* ✅ Scrollable Container */
.reviews-wrapper {
    display: flex;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
    gap: 16px;
    padding-bottom: 10px;
    scrollbar-width: none; /* Hide scrollbar for Firefox */
    -ms-overflow-style: none; /* Hide scrollbar for IE/Edge */
    cursor: grab;
}

/* Hide scrollbar for Chrome/Safari */
.reviews-wrapper::-webkit-scrollbar {
    display: none;
}

/* ✅ Review Card */
.review-card {
    flex: 0 0 260px; /* Fixed card width */
    height: 360px;
    border-radius: 12px;
    background-size: cover;
    background-position: center;
    scroll-snap-align: start;
    position: relative;
}

/* ✅ Play Button */
.play-button {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    background: rgba(255, 255, 255, 0.05);
    border-radius: 50%;
    padding: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.play-button img {
    width:54px;
    height: 54px;
}
</style>