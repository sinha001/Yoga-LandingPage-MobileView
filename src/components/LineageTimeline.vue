<template>
    <section class="section">
      <div class="container">
        <p class="section-tagline">OUR LINEAGE</p>
        <h2 class="section-title">
          5000 Years Old Yoga Tradition <br> Of The Himalayan Masters
        </h2>
  
        <div class="timeline">
          <div v-for="(master, index) in masters" :key="index" class="timeline-item" :class="{ 'reverse': index % 2 !== 0 }">
            <!-- Image Column -->
            <div class="col-image">
              <img :src="master.image" alt="Master Image" class="timeline-image" />
            </div>
  
            <!-- Text Column -->
            <div class="col-text">
              <!-- Conditional Extra Title (Date/Period) -->
              <p v-if="master.extraTitle" class="timeline-extra-title">{{ master.extraTitle }}</p>
              <h3 class="timeline-title">{{ master.name }}</h3>
              <p class="timeline-description">{{ master.description }}</p>
            </div>
  
            <!-- Connecting Line -->
            <div v-if="index < masters.length - 1" class="connecting-line-wrapper">
              <img :src="connectingLine" alt="Connecting Line" class="connecting-line" :class="{ 'flip': index % 2 !== 0 }" />
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        masters: [
          {
            name: "Agastya Muni",
            description: "He is the author of some verses of Rig Veda, He is the one of the most seven revered rishi, one of the siddha of shavism tradition.",
            image: new URL('../assets/agstya-images/image (2).png', import.meta.url).href
          },
          {
            name: "Patanjali (4th Century BC)",
            description: "A great Raja Yogi of Siddha Tradition, Writer of Yoga Sutra- here he brought all 4000 yoga tradition in 196 sutras and make easy.",
            image: new URL('../assets/agstya-images/image.png', import.meta.url).href
          },
          {
            name: "Siddha Bhogar (550 BC)",
            description: "A great Siddha accomplished yogi and disciple of Agastya Muni.",
            image: new URL('../assets/agstya-images/image-1.png', import.meta.url).href
          },
          {
            extraTitle: "30 NOV 203 AD - PRESENT",
            name: "Mahavatar Babaji",
            description: "An immortal yogi of Himalaya, disciple of Siddha Bhogar Nather.",
            image: new URL('../assets/agstya-images/image-2.png', import.meta.url).href
          },
          {
            name: "Lahiri Mahasaya",
            description: "A Himalayan Yogi disciple of Mahavatar Babaji.",
            image: new URL('../assets/agstya-images/image-3.png', import.meta.url).href
          },
          {
            extraTitle: "(1925-1996)",
            name: "Swami Rama (1925-1996)",
            description: "A Himalayan Yogi disciple of Bengali Baba.",
            image: new URL('../assets/agstya-images/image-4.png', import.meta.url).href
          },
          {
            extraTitle: "(1933-2015)",
            name: "Swami Veda Bharati",
            description: "Founder of AHYMSIN, a great yogi and writer of many yoga books. (Disciple of Swami Rama of the Himalayas).",
            image: new URL('../assets/agstya-images/image-5.png', import.meta.url).href
          },
          {
            name: "Yogi Pramod Sahu",
            description: "Leading Master of yoga and meditation of the ancient Himalayan Tradition. He is the disciple of Swami Veda Bharati and founder of Hari Om Yoga Vidya School.",
            image: new URL('../assets/agstya-images/image (1).png', import.meta.url).href
          }
        ],
        connectingLine: new URL('../assets/Images/Vector 14.png', import.meta.url).href
      };
    }
  };
  </script>
  
  <style scoped>
  /* Section Styling */
  .section {
    background: #fff;
    padding: 48px 24px;
    text-align: center;
  }
  
  /* Tagline */
  .section-tagline {
    font-size: 14px;
    color: #ff6600;
    font-weight: 400;
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-bottom: 8px;
  }
  
  /* Title */
  .section-title {
    font-size: 28px;
    color: #734875;
    font-weight: 400;
    line-height: 1.3;
    letter-spacing: -1px;
    margin-bottom: 32px;
  }
  
  /* Timeline */
  .timeline {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  /* Timeline Item */
  .timeline-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    margin-bottom: 0;
    position: relative;
  }
  
  /* Reverse for Even Rows */
  .timeline-item.reverse {
    flex-direction: row-reverse;
  }
  
  /* Text Column */
  .col-text {
    flex: 2;
    text-align: left;
    padding: 10px;
  }
  
  /* Extra Title (Date/Period) */
  .timeline-extra-title {
    font-size: 12px;
    color: #ff6600;
    font-weight: 500;
    margin-bottom: 4px;
    text-transform: uppercase;
  }
  
  /* Image Column */
  .col-image {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
  }
  
  /* Image */
  .timeline-image {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    border: 2px solid #ff8b61;
    position: relative;
    z-index: 1;
    padding:0.5px;
  }
  
  /* Connecting Line */
  .connecting-line-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    position: absolute;
    bottom: -20px;
  }
  
  .connecting-line {
    width: 284px;
    height: 60px;
    position: relative;
    top: 10px;
    z-index: 0;
  }
  
  /* Flip Connecting Line for Alternate Rows */
  .flip {
    transform: scaleX(-1);
  }
  
  /* Text Formatting */
  .col-text .timeline-title {
    font-size: 16px;
    letter-spacing: 0;
    font-weight: 500;
  }
  
  .col-text .timeline-description {
    font-size: 12px;
    letter-spacing: 0;
    font-weight: 400;
  }
  </style>
  