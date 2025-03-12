<template>
    <div class="gallery-section">
        <p class="section-highlight">OUR GALLERY</p>
        <h2 class="section-title">Admire moments we captured for You</h2>

        <div class="gallery-container">
            <!-- ✅ First Row: Scrolls LTR -->
            <div class="scroll-wrapper rt1" ref="rowOne">
                <div v-for="(image, index) in firstRow" :key="index" class="gallery-item">
                    <img :src="image" alt="Gallery Image" />
                </div>
            </div>

            <!-- ✅ Second Row: Scrolls RTL -->
            <div class="scroll-wrapper rt2" ref="rowTwo">
                <div v-for="(image, index) in secondRow" :key="index" class="gallery-item">
                    <img :src="image" alt="Gallery Image" />
                </div>
            </div>

            <!-- ✅ Third Row: Scrolls LTR -->
            <div class="scroll-wrapper rt1" ref="rowThree">
                <div v-for="(image, index) in thirdRow" :key="index" class="gallery-item">
                    <img :src="image" alt="Gallery Image" />
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

// ✅ Dynamic Data
const firstRow = ref([
    new URL("../assets/row1/Placeholder Image 2.png", import.meta.url).href,
    new URL("../assets/row1/Placeholder Image 3.png", import.meta.url).href,
    new URL("../assets/row1/Placeholder Image 4.png", import.meta.url).href,
    new URL("../assets/row1/Placeholder Image 5.png", import.meta.url).href,
    new URL("../assets/row1/Placeholder Image 6.png", import.meta.url).href
]);

const secondRow = ref([
    new URL("../assets/row2/Placeholder Image 7.png", import.meta.url).href,
    new URL("../assets/row2/Placeholder Image 8.png", import.meta.url).href,
    new URL("../assets/row2/Placeholder Image 9.png", import.meta.url).href,
    new URL("../assets/row2/Placeholder Image 10.png", import.meta.url).href,
    new URL("../assets/row2/Placeholder Image 11.png", import.meta.url).href
]);

const thirdRow = ref([
    new URL("../assets/row3/Placeholder Image 2-1.png", import.meta.url).href,
    new URL("../assets/row3/Placeholder Image 3-1.png", import.meta.url).href,
    new URL("../assets/row3/Placeholder Image 4-1.png", import.meta.url).href,
    new URL("../assets/row3/Placeholder Image 5.png", import.meta.url).href,
    new URL("../assets/row3/Placeholder Image 6.png", import.meta.url).href
]);

// ✅ Function to enable drag scrolling
const enableDragScroll = (element) => {
    let isDown = false;
    let startX;
    let scrollLeft;

    element.addEventListener("mousedown", (e) => {
        isDown = true;
        startX = e.pageX - element.offsetLeft;
        scrollLeft = element.scrollLeft;
        element.style.cursor = "grabbing";
    });

    element.addEventListener("mouseleave", () => {
        isDown = false;
        element.style.cursor = "grab";
    });

    element.addEventListener("mouseup", () => {
        isDown = false;
        element.style.cursor = "grab";
    });

    element.addEventListener("mousemove", (e) => {
        if (!isDown) return;
        e.preventDefault();
        const x = e.pageX - element.offsetLeft;
        const walk = (x - startX) * 2;
        element.scrollLeft = scrollLeft - walk;
    });
};

// ✅ Apply drag-scroll on mount
onMounted(() => {
    enableDragScroll(document.querySelector(".rt1"));
    enableDragScroll(document.querySelector(".rt2"));
    enableDragScroll(document.querySelector(".rt1:last-child"));
});
</script>

<style scoped>

.gallery-section {
    background-color: #FFF8F4;
    text-align: center;
    padding: 48px 0;
}

.section-highlight {
    color: #FF6600;
    font-size: 12px;
    font-weight: 400;
    letter-spacing: 1px;
    padding:0 24px; 

}

.section-title {
    font-size: 28px;
    color: #4F2553;
    font-weight: 500;
    margin-bottom: 16px;
    padding:0 24px; 

}

.gallery-container {
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.scroll-wrapper {
    display: flex;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
    gap: 16px;
    padding-bottom: 10px;
    scrollbar-width: none;
    -ms-overflow-style: none;
    cursor: grab;
    scroll-behavior: smooth;
}

.scroll-wrapper::-webkit-scrollbar {
    display: none;
}

.rt2 {
    flex-direction: row;
    padding-left:24px !important;

}

.scroll-wrapper.rt2 {
    flex-direction: row !important;
    padding:0 24px !important;
}


.rt1{
    flex-direction: row-reverse;
    padding: 0 24px 0 0;

}

.gallery-item {
    flex: 0 0 160px;
    height: 160px;
    min-width: 150px;
    border-radius: 12px;
    overflow: hidden;
    scroll-snap-align: start;
}

.gallery-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 12px;
}
</style>