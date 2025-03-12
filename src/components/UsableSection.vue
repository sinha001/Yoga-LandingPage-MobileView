<template>
  <section class="section" :style="{ backgroundColor: bgColor }">
    <div class="container">
      <p v-if="tagline" class="section-tagline">{{ tagline }}</p>
      <h2 v-if="title" class="section-title" v-html="title"></h2>

      <div class="stats-grid">
        <div class="stats-card" :style="{ backgroundColor: statsColor }" v-for="(stat, index) in stats" :key="index">
          <h3 class="stats-number">{{ stat.number }}</h3>
          <p class="stats-text">{{ stat.text }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    tagline: {
      type: String,
      required: false
    },
    stats: {
      type: Array,
      required: true
    },
    bgColor: {
      type: String,
      default: "#fdf3f0" // Default background color
    },
    statsColor: {
      type: String,
      default: "#ffffff" // Default background color
    }
  }
};
</script>

<style scoped>
.section {
  padding: 48px 24px;
  text-align: left;
  transition: background-color 0.3s ease-in-out; /* Smooth transition */
}

.section-tagline {
  font-size: 14px;
  color: #ff6600;
  font-weight: 600;
  letter-spacing: 1px;
  text-transform: uppercase;
  margin-bottom: 8px;
}

.section-title {
  font-size: 32px;
  color: #734875;
  font-weight: 400;
  line-height: 1.3;
  letter-spacing: 0;
  margin-bottom: 24px;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(140px, 1fr));
  gap: 16px;
  justify-content: center;
}

.stats-card {
  background: transparent;
  border: 2px solid #ff8b61;
  border-radius: 12px;
  padding: 12px;
  text-align: left;
  min-width: 108px;
  min-height: 80px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.stats-number {
  font-size: 24px;
  font-weight: 600;
  color: #1d1d1d;
  margin-bottom: 4px;
  letter-spacing: 0;
}

.stats-text {
  font-size: 12px;
  font-weight: 400;
  letter-spacing: 0;
  color: #555;
}

@media (max-width: 480px) {
  .stats-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
