<template>
    <section class="daily-schedule mt-4 py-4">
      <div class="container text-center">
        <h2 class="schedule-title">{{ title }}</h2>
        <p class="schedule-subtitle">{{ subtitle }}</p>
  
        <!-- Schedule Box (Divided into Two Columns) -->
        <div class="schedule-box p-3 mt-3">
          <div class="schedule-container">
            <!-- Left Column -->
            <div class="schedule-column">
              <div v-for="(item, index) in leftColumn" :key="index" class="schedule-item">
                <p class="time">{{ item.time }}</p>
                <p class="activity">{{ item.activity }}</p>
              </div>
            </div>
  
            <!-- Vertical Line Separator -->
            <div class="schedule-divider"></div>
  
            <!-- Right Column -->
            <div class="schedule-column">
              <div v-for="(item, index) in rightColumn" :key="index" class="schedule-item">
                <p class="time">{{ item.time }}</p>
                <p class="activity">{{ item.activity }}</p>
              </div>
            </div>
          </div>
        </div>
  
        <button class="btn btn-download mt-3">
          <img src="..\assets\Images\line-md_downloading-loop.png"/> {{ buttonText }}
        </button>
      </div>
    </section>
  </template>
  
  <script>
  import { ref, computed } from "vue";
  
  export default {
    setup() {
      const title = ref("Daily Schedule");
      const subtitle = ref("Designed to Equip You with Holistic Yoga Knowledge and Skills");
      const buttonText = ref("Download Curriculum");
  
      const schedule = ref([
        { time: "06:30 AM – 08:00 AM", activity: "Traditional Hatha Yoga & Alignments" },
        { time: "08:30 AM – 09:30 AM", activity: "Breakfast Time" },
        { time: "10:15 AM – 11:15 AM", activity: "Kundalini Yoga" },
        { time: "11:30 AM – 01:00 PM", activity: "Meditation, Pranayama, Mudra, Bandha, & Satkarma" },
        { time: "01:00 PM – 02:00 PM", activity: "Delicious Indian Lunch" },
        { time: "02:00 PM – 03:00 PM", activity: "Alignment & Adjustment" },
        { time: "03:00 PM – 04:00 PM", activity: "Yoga Philosophy & Ayurveda" },
        { time: "04:00 PM – 05:00 PM", activity: "Self Study" },
        { time: "05:30 PM – 07:00 PM", activity: "Ashtanga Vinyasa & Alignments" },
        { time: "07:00 PM – 08:00 PM", activity: "Enjoy Your Dinner" },
        { time: "08:00 PM – 09:00 PM", activity: "Home Work & Assignments" },
        { time: "09:00 PM", activity: "Rest Time" },
      ]);
  
      // Split schedule into two equal columns
      const middleIndex = Math.ceil(schedule.value.length / 2);
      const leftColumn = computed(() => schedule.value.slice(0, middleIndex));
      const rightColumn = computed(() => schedule.value.slice(middleIndex));
  
      return { title, subtitle, buttonText, leftColumn, rightColumn };
    }
  };
  </script>
  
  <style scoped>
  .daily-schedule {
    padding: 48px 24px;
    background: #fdf3f0;
  }
  
  .schedule-title {
    font-size: 36px;
    font-weight: 400;
    letter-spacing: 0;
    color: #734875;
  }
  
  .schedule-subtitle {
    font-size: 14px;
    font-weight: 400;
    letter-spacing: 0;
    color: #455A64;
  }
  
  .schedule-box {
    background: #fff;
    border-radius: 12px;
    border: 1px solid #ff8b61;
    padding: 20px;
  }

  .schedule-container {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
  }

  .schedule-column {
    width: 46%;
  }
  
  /* Vertical Divider */
  .schedule-divider {
    width: 2px;
    background: #ddd;
    height: 100%;
  }


  .schedule-item {
    text-align: left;
    padding: 16px 0;
    border-bottom: 1px solid rgba(245, 174, 100, 0.5);
  }
  
  .schedule-item:last-child {
    border-bottom: none;
  }
  
  .time {
    font-size: 10px;
    font-weight: 400;
    letter-spacing: 0;
    color: #FF5E14;
    margin-bottom: 0;
  }
  
  .activity {
    font-size: 14px;
    font-weight: 400;
    letter-spacing: 0;
    color: #455A64;
    margin-bottom: 0;

  }
  
  .btn-download {
    border: 1px solid #734875;
    color: #734875;
    width: 253px;
    height: 48px;
    padding: 8px 10px 8px 6px;
    border-radius: 12px;
    font-weight: 500;
    text-align: center;
    letter-spacing: 0;
  }
  
  .btn-download i {
    margin-right: 5px;
    width: 28px;
    height: 28px;
  }
  </style>
  