<template>
    <div class="phase-container">
        <div class="phase-card">
            <p class="phase-badge">{{ phase }}</p>
            <div class="phase-content">
                <h2 class="phase-title">{{ title }}</h2>
                <h3 v-if="subtitle" class="phase-subtitle">{{ subtitle }}</h3>

                <div class="phase-list-grid">
                    <ul v-for="(column, index) in splitItems" :key="index">
                        <li v-for="(item, i) in column" :key="i">
                            <span class="icon">✦</span> {{ item }}
                        </li>
                    </ul>
                </div>
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
        title: {
            type: String,
            required: true
        },
        subtitle: {
            type: String,
            required: false
        },
        items: {
            type: Array,
            required: true
        },
        columns: {
            type: Number,
            default: 1 // Number of columns for the list
        }
    },
    computed: {
        splitItems() {
            let colSize = Math.ceil(this.items.length / this.columns);
            return Array.from({ length: this.columns }, (_, i) =>
                this.items.slice(i * colSize, (i + 1) * colSize)
            );
        }
    }
};
</script>

<style scoped>
.phase-container{
    padding: 10px 24px;
}
.phase-card {
    background: #fff7f2;
    border-radius: 12px;
    padding: 20px;
    border: 1px solid #ff8b61;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
    text-align: left;
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

.phase-list-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    /* Dynamic columns */
    gap: 16px;
    padding: 0;
}

.phase-list-grid ul {
    list-style: none;
    padding: 0;
}

.phase-list-grid li {
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