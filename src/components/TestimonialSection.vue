<template>
    <section class="testimonial-section">
      <div class="container">
        <h2 class="testimonial-section-title text-center">
          Why Our Students<br> Choose Us?
        </h2>
  
        <!-- Scrollable Testimonial Container -->
        <div ref="scrollContainer" class="testimonial-scroll">
          <div class="testimonial-wrapper">
            <!-- Loop through testimonials -->
            <div
              class="testimonial-card p-4"
              v-for="(testimonial, index) in testimonials"
              :key="index"
            >
              <div class="d-flex justify-content-between align-items-center">
                <img
                  :src="testimonial.platformLogo"
                  alt="Platform"
                  class="platform-logo"
                />
  
                <div class="stars">
                  <img :src="testimonial.ratingImage" alt="Rating" />
                </div>
              </div>
  
              <p class="testimonial-text">
                {{ testimonial.text }}
              </p>
  
              <div class="d-flex align-items-center">
                <img :src="testimonial.userImage" alt="User" class="user-img" />
                <div>
                  <p class="user-name">{{ testimonial.userName }}</p>
                  <p class="user-role">{{ testimonial.userRole }}</p>
                </div>
              </div>
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
        testimonials: [
          {
            platformLogo: new URL('../assets/Images/flat-color-icons_google.png', import.meta.url).href,
            ratingImage: new URL('../assets/Images/Frame 1138.png', import.meta.url).href,
            text: "The 200-hour Yoga Teacher Training program at Hari Om Yoga Vidya School was a life-changing experience. The knowledgeable instructors, serene environment, and comprehensive curriculum provided the perfect foundation for my yoga journey. I highly recommend this program to anyone seeking to deepen their practice and become a certified yoga teacher.",
            userImage: new URL('../assets/Images/Ellipse 300.png', import.meta.url).href,
            userName: "Rayna Westervelt",
            userRole: "200 Hour YTT Student",
          },
          {
            platformLogo: new URL('../assets/Images/Frame 1141.png', import.meta.url).href,
            ratingImage: new URL('../assets/Images/Frame 1138.png', import.meta.url).href,
            text: "The 200-hour Yoga Teacher Training program at Hari Om Yoga Vidya School was a life-changing experience. The knowledgeable instructors, serene environment, and comprehensive curriculum provided the perfect foundation for my yoga journey. I highly recommend this program to anyone seeking to deepen their practice and become a certified yoga teacher.",
            userImage: new URL('../assets/Images/Ellipse 300.png', import.meta.url).href,
            userName: "Rayna Westervelt",
            userRole: "500 Hour YTT Graduate",
          },
          {
            platformLogo: new URL('../assets/Images/flat-color-icons_google.png', import.meta.url).href,
            ratingImage: new URL('../assets/Images/Frame 1138.png', import.meta.url).href,
            text: "The 200-hour Yoga Teacher Training program at Hari Om Yoga Vidya School was a life-changing experience. The knowledgeable instructors, serene environment, and comprehensive curriculum provided the perfect foundation for my yoga journey. I highly recommend this program to anyone seeking to deepen their practice and become a certified yoga teacher.",
            userImage: new URL('../assets/Images/Ellipse 300.png', import.meta.url).href,
            userName: "Rayna Westervelt",
            userRole: "200 Hour YTT Student",
          },
          {
            platformLogo: new URL('../assets/Images/Frame 1141.png', import.meta.url).href,
            ratingImage: new URL('../assets/Images/Frame 1138.png', import.meta.url).href,
            text: "The 200-hour Yoga Teacher Training program at Hari Om Yoga Vidya School was a life-changing experience. The knowledgeable instructors, serene environment, and comprehensive curriculum provided the perfect foundation for my yoga journey. I highly recommend this program to anyone seeking to deepen their practice and become a certified yoga teacher.",
            userImage: new URL('../assets/Images/Ellipse 300.png', import.meta.url).href,
            userName: "Rayna Westervelt",
            userRole: "500 Hour YTT Graduate",
          },
          {
            platformLogo: new URL('../assets/Images/flat-color-icons_google.png', import.meta.url).href,
            ratingImage: new URL('../assets/Images/Frame 1138.png', import.meta.url).href,
            text: "The 200-hour Yoga Teacher Training program at Hari Om Yoga Vidya School was a life-changing experience. The knowledgeable instructors, serene environment, and comprehensive curriculum provided the perfect foundation for my yoga journey. I highly recommend this program to anyone seeking to deepen their practice and become a certified yoga teacher.",
            userImage: new URL('../assets/Images/Ellipse 300.png', import.meta.url).href,
            userName: "Rayna Westervelt",
            userRole: "200 Hour YTT Student",
          },
          {
            platformLogo: new URL('../assets/Images/Frame 1141.png', import.meta.url).href,
            ratingImage: new URL('../assets/Images/Frame 1138.png', import.meta.url).href,
            text: "The 200-hour Yoga Teacher Training program at Hari Om Yoga Vidya School was a life-changing experience. The knowledgeable instructors, serene environment, and comprehensive curriculum provided the perfect foundation for my yoga journey. I highly recommend this program to anyone seeking to deepen their practice and become a certified yoga teacher.",
            userImage: new URL('../assets/Images/Ellipse 300.png', import.meta.url).href,
            userName: "Rayna Westervelt",
            userRole: "500 Hour YTT Graduate",
          },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  .testimonial-section {
    padding: 48px 24px;
  }
  
  .testimonial-section-title {
    font-size: 32px;
    font-weight: 400;
    color: #734875;
    margin-bottom: 32px;
  }
  
  .testimonial-scroll {
    overflow-x: auto; 
    scroll-behavior: smooth; 
    scroll-snap-type: x mandatory; 
    white-space: nowrap;
    padding-bottom:0 0 16px 0;
    display: flex;
    justify-content: flex-start;
    min-height: 442px; 
    margin: 0;
  }
  
  .testimonial-wrapper {
    display: flex;
    gap: 26px;
  }
  
  .testimonial-card {
    background: #F8F6F8;
    border-radius: 12px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    padding: 24px;
    text-align: center;
    width: 80%;
    max-width: 350px;
    flex: 0 0 auto;
    flex-shrink: 0;
    scroll-snap-align: center; 
    display: flex;
    flex-direction: column; 
  }
    .testimonial-text {
    font-size: 14px;
    line-height: 1.5;
    color: #111;
    margin: 24px 0;
    text-align: start;
    white-space: normal; 
    max-width: 100%; 
    overflow-wrap: break-word; 
  }
  
  .platform-logo {
    width: 32px;
    height: auto;
  }
  
  .stars img {
    width: 100px;
  }
  
  .user-img {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    margin-right: 10px;
  }
  
  .user-name {
    font-size: 14px;
    font-weight: 600;
    margin: 0;
  }
  
  .user-role {
    font-size: 12px;
    color: #666;
    margin: 0;
  }
  
  .testimonial-scroll::-webkit-scrollbar {
    display: none;
  }
  
  
  </style>
  