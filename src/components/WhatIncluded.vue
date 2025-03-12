<template>
  <div class="include-section">
      <div class="include-container">
          <div class="image-wrapper">
              <!-- Rotating Background Image -->
              <img src="../assets/Images/Group.png" alt="Rotating Lotus" class="rotating-image" />
      
              <!-- Centered Logo -->
              <img src="../assets/Images/mdi_om.png" alt="Yoga School Logo" class="center-logo" />
          </div>

          <!-- Content Section -->
          <div class="content-section">
              <p class="section-highlight">WHAT’S INCLUDED IN THE COURSE</p>
              <h2 class="section-title">Comfortable Accommodations<br> for Your Yoga Journey</h2>
              <p class="section-subtitle">
                  Enhance Your Yoga Journey with Exclusive Perks & Activities.
              </p>

              <div class="columns">
                  <ul class="column">
                      <li><span class="icon yoga"></span> Free Yoga Equipment</li>
                      <li><span class="icon wifi"></span> Free WiFi</li>
                      <li><span class="icon meals"></span> 3 Vegetarian Meals Everyday</li>
                      <li><span class="icon kitbag"></span> Yoga Kitbag</li>
                      <li><span class="icon water"></span> 24 Hours Hot Water</li>
                      <li><span class="icon excursion"></span> Excursion of Rishikesh</li>
                      <li><span class="icon study"></span> Study Materials</li>
                      <li><span class="icon shopping"></span> Help for Shopping in Rishikesh</li>
                  </ul>
                  
                  <ul class="column">
                      <li><span class="icon accommodation"></span> 26 Nights Accommodation</li>
                      <li><span class="icon calendar"></span> 2nd - 28th of each month</li>
                      <li><span class="icon pickup"></span> Free Airport Pick-Up</li>
                      <li><span class="icon certificate"></span> Yoga Alliance Certificate</li>
                      <li><span class="icon classes"></span> 8 hours long classes</li>
                      <li><span class="icon ganga"></span> Classes at Ganga Beach</li>
                      <li><span class="icon culture"></span> Cultural Program</li>
                      <li><span class="icon fire"></span> Fire Ceremony</li>
                      <li><span class="icon more"></span> And more...</li>
                  </ul>
              </div>
          </div>
      </div>
  </div>
</template>

<style scoped>
.include-section {
  padding: 0 24px 48px 24px;
  background: linear-gradient(to bottom, #FFF8F4 0%, rgba(255,248,244,0) 30%, rgba(255,248,244,0) 100%);
}

.image-wrapper {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%; 
  height: 220px;
}

.rotating-image {
  width: 165px;
  height: 165px;
  position: absolute;
  animation: rotateAnimation 30s linear infinite;
}

.center-logo {
  width: 92px;
  height: 92px;
  position: relative;
  z-index: 1; 
  bottom: 2%;
}

@keyframes rotateAnimation {
  from {
      transform: rotate(0deg);
  }
  to {
      transform: rotate(360deg);
  }
}

.content-section{
  margin-top: 32px;
  height: 570px;
}

/* Text Styling */
.section-highlight {
  text-align: center;
  color: #FF5E14;
  font-size: 12px;
  font-weight: 400;
  letter-spacing: 2px;
  margin-bottom: 8px;
}

.section-title {
  text-align: center;
  font-size: 30px;
  color: #734875;
  font-weight: 400;
  letter-spacing: -1px;
  margin-bottom: 24px;
}

.section-subtitle {
  text-align: center;
  font-size: 16px;
  font-family: 400;
  color: #455A64;
  letter-spacing: 0;
  margin-bottom: 24px;
}

/* Columns */
.columns {
  display: flex;
  justify-content: space-between;
  text-align: left;
  gap: 16px;
}

.column {
  width: 50%;
  padding: 0;
  list-style: none;
  font-size: 12px;
  letter-spacing: 0;
  font-family: 400;
  color: #455A64;
}

.column li {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 16px;
}

/* Icons */
.icon {
  display: inline-block;
  width: 20px;
  height: 20px;
  background-size: contain;
  background-repeat: no-repeat;
}

/* Customizable Icons */
.yoga { background-image: url('../assets/icons-svg/verified.png'); }
.wifi { background-image: url('../assets/icons-svg/nest_remote_comfort_sensor.png'); }
.meals { background-image: url('../assets/icons-svg/restaurant.png'); }
.kitbag { background-image: url('../assets/icons-svg/your_trips.png'); }
.water { background-image: url('../assets/icons-svg/bathtub.png'); }
.excursion { background-image: url('../assets/icons-svg/mountain_flag.png'); }
.study { background-image: url('../assets/icons-svg/book_5.png'); }
.shopping { background-image: url('../assets/icons-svg/so-shopping-bag-ui.png'); }

.accommodation { background-image: url('../assets/icons-svg/family_home.png'); }
.calendar { background-image: url('../assets/icons-svg/calendar_month.png'); }
.pickup { background-image: url('../assets/icons-svg/taxi, car, airport.png'); }
.certificate { background-image: url('../assets/icons-svg/award_star.png'); }
.classes { background-image: url('../assets/icons-svg/timelapse.png'); }
.ganga { background-image: url('../assets/icons-svg/beach_access.png'); }
.culture { background-image: url('../assets/icons-svg/energy_program_saving.png'); }
.fire { background-image: url('../assets/icons-svg/local_fire_department.png'); }
.more { background-image: url('../assets/icons-svg/lets-icons_check-ring-duotone.png'); }
</style>
