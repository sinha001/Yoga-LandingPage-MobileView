<template>
    <div class="phase-container">
        <div class="phase-card">
            <p class="phase-badge">
                {{ phase }}
            </p>
            <img :src="image" alt="Phase Image" class="phase-image">

            <div class="phase-content">
                <h2 class="phase-title">
                    {{ title }}
                </h2>
                <h3 class="phase-subtitle">{{ subtitle }}</h3>

                <ul class="phase-list">
                    <li v-for="(item, index) in items" :key="index">
                        <span class="icon">✦</span>{{ item }}
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        phase: {
            type: String,
            required: true
        },
        image: {
            type: String,
            required: true
        },
        title: {
            type: String,
            required: true
        },
        subtitle: {
            type: String,
            required: true
        },
        items: {
            type: Array,
            required: true
        },

    }
};
</script>

<style scoped>
.phase-container{
    padding: 10px 24px;
}
.phase-card {
    background-color: #fff7f2;
    border-radius: 12px;
    padding: 24px 20px;
    border: 1px solid #ff8b61;
    text-align: start;
}

.phase-badge {
    background: rgba(255,174,100,0.5);
    color: #455A64;
    font-weight: 500;
    padding: 6px 12px;
    border-radius: 20px;
    display: inline-block;
    margin-bottom: 12px;
    font-size: 12px;
}

.phase-image {
    width: 100%;
    border-radius: 10px;
    margin-bottom: 16px;
}

.phase-content {
    padding: 10px 0;
}

.phase-title {
    font-size: 20px;
    font-weight: 500;
    color: #333;
    margin-bottom: 16px;
    letter-spacing: 0;
}
.phase-subtitle{
    font-size: 14px;
    font-weight: 500;
    letter-spacing: 0;
    color: #455A64;
    margin-bottom: 8px;
}
.phase-list {
    list-style: none;
    padding: 0;
}

.phase-list li {
    display: flex;
    align-items: center;
    font-size: 12px;
    font-weight: 400;
    color: #555;
    margin-bottom: 8px;
}

.icon {
    color: #734875;
    margin-right: 8px;
}
</style>