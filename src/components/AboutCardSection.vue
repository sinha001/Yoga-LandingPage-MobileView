<template>
    <div class="container card-section ">
        <div class="row">
            <div class="col-12 col-md-6" v-for="(card, index) in cards" :key="index">
                <div class="info-card">
                    <img :src="card.image" alt="Yoga Pose" class="card-image" />
                    <h3 class="card-title text-start">{{ card.title }}</h3>
                    <p class="card-subtitle text-start">{{ card.subtitle }}</p>
                    <div class="card-content">
                        <div class="card-item" v-for="(item, i) in card.items" :key="i">
                            <div class="item-header" @click="toggleItem(index, i)">
                                <span>{{ item.title }}</span>
                                <span class="plus-icon">{{ expandedItems[index] && expandedItems[index][i] ? '-' : '+' }}</span>
                            </div>
                            <p v-if="expandedItems[index] && expandedItems[index][i]" class="item-description">{{ item.description }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';

defineProps({
    cards: Array
});

const expandedItems = ref({});

const toggleItem = (cardIndex, itemIndex) => {
    if (!expandedItems.value[cardIndex]) {
        expandedItems.value[cardIndex] = {};
    }
    expandedItems.value[cardIndex][itemIndex] = !expandedItems.value[cardIndex][itemIndex];
};
</script>

<style scoped>
.card-section {
    padding: 30px 0;
}

.info-card {
    border-radius: 12px;
    padding: 20px;
    text-align: center;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    border: 1px solid #F5AE64;
    margin-bottom: 20px;
    overflow: hidden;
}

.card-image {
    width: 100%;
    border-radius: 12px;
}

.card-title {
    font-size: 28px;
    color: #734875;
    font-weight: 400;
    margin-top: 15px;
}

.card-subtitle {
    font-size: 28px;
    color: #734875;
    font-weight: 400;
    margin-bottom: 15px;
}

.card-content {
    display: flex;
    flex-direction: column;
    gap: 10px;
    overflow: hidden;
}

.card-item {
    padding: 10px 15px;
    border-radius: 8px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
    text-align: start;
    font-size: 16px;
    color: #734875;
    font-weight: 500;
    cursor: pointer;
    background-color: #FFF8F4;

}

.item-header {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.plus-icon {
    font-size: 20px;  
    font-weight: bold;
    background-color: #FFEEEA;
    width: 30px;  
    height: 30px; 
    border-radius: 5px;
    display: flex;
    align-items: center;
    justify-content: center;
    line-height: 1; 
    position: relative;
    transition: transform 10s ease-in-out, background-color 10s ease-in-out;
}


.item-description {
    font-size: 14px;
    color: #555;
    margin-top: 5px;
    text-align: left;
}
</style>
