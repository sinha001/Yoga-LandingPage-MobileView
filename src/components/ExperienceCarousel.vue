<template>
    <div class="container carousel-container mb-4">
        <div class="carousel-wrapper">
            <div class="carousel-track">
                <div class="carousel-item" v-for="(item, index) in items" :key="index">
                    <h3 class="exp-number">{{ item.number }}</h3>
                    <p class="exp-text">{{ item.text }}</p>
                </div>
                <!-- Duplicate Items for Infinite Loop Effect -->
                <div class="carousel-item" v-for="(item, index) in items" :key="'duplicate-' + index">
                    <h3 class="exp-number">{{ item.number }}</h3>
                    <p class="exp-text">{{ item.text }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const items = [
    { number: "15+", text: "Years Experience" },
    { number: "3000+", text: "Students Trained" },
    { number: "Certified", text: "Masters" },
    { number: "Premium", text: "Accommodation" },
    { number: "Safe", text: "Environment" }

];
</script>

<style scoped>
.carousel-container {
    width: 100%;
    overflow: hidden;
    position: relative;
    height: 60px;
    margin-top: -40px;
}

.carousel-wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
}

.carousel-track {
    display: flex;
    gap: 40px;
    width: max-content; /* Adjust width based on item count */
    animation: slide 12s linear infinite;
   
}

/* Each carousel item */
.carousel-item {
    display: block;
    min-width: 150px;
    text-align: center;
    margin-right: 0 !important;
}

.exp-number {
    font-size: 24px;
    font-weight: 700;
    color: #734875;
}

.exp-text {
    font-size: 14px;
    color: #734875;
}

.exp-number, .exp-text {
    color: #734875 !important; /* Ensure text is visible */
}


/* Looping Animation */
@keyframes slide {
    0% {
        transform: translateX(0);
    }
    100% {
        transform: translateX(-50%);
    }
}
</style>
