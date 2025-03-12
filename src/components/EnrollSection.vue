<template>
    <section class="enroll-section">
      <div class="enroll-container">
        <div class="enroll-content">
          <p class="enroll-tagline">LIMITED-TIME OFFER</p>
          <h2 class="enroll-title">Enroll Now & Receive <br> Exclusive Bonuses</h2>
  
          <div class="enroll-benefits">
            <div class="benefit"><i class="bi bi-check-circle-fill"></i> FREE Ayurveda Class</div>
            <div class="benefit"><i class="bi bi-check-circle-fill"></i> FREE Prenatal Yoga Class</div>
            <div class="benefit"><i class="bi bi-check-circle-fill"></i> FREE Sound Healing Classes</div>
          </div>
  
          <p class="enroll-warning">Only 10 Spots Left - Prices Increase Soon!</p>
  
          <a href="#" class="enroll-button">Claim before it ends!</a>
        </div>
      </div>
    </section>
  </template>
  
  <style scoped>
  .enroll-section {
    position: relative;
    width: 100%;
    border-radius: 12px;
    overflow: hidden;
    text-align: center;
    padding: 48px 24px;
  }
  
  .enroll-container {
    background: url("../assets/Images/enroll-background.png") no-repeat center center / cover;
    position: relative;
    padding: 20px 10px;
    border-radius: 12px !important;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 400px;
  }
  
  .enroll-container::before {
    content: "";
    position: absolute;
    inset: 0;
    background: rgba(0, 0, 0, 0.5);
    z-index: 1;
    border-radius: 12px;
  }
  
  .enroll-content {
    position: relative;
    z-index: 1;
    color: white;
    max-width: 90%;
  }
  
  .enroll-tagline {
    text-transform: uppercase;
    font-size: 12px;
    letter-spacing: 1px;
    opacity: 0.8;
    margin-bottom: 8px;
  }
  
  .enroll-title {
    font-size: 24px;
    font-weight: 600;
    margin-bottom: 16px;
    line-height: 1.4;
    letter-spacing: 0;

  }
  
  .enroll-benefits {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 8px;
    margin-bottom: 16px;

  }
  
  .benefit {
    display: flex;
    align-items: center;
    gap: 6px;
    background: rgba(255, 255, 255, 0.2);
    padding: 6px 10px;
    border-radius: 20px;
    font-size: 12px;
    font-family: 400;
    letter-spacing: -0.5px;
  }
  
  .benefit i {
    color: rgba(199, 196, 196, 0.874);
    font-size: 16px;
  }
  
  .enroll-warning {
    font-size: 14px;
    margin-bottom: 20px;
    opacity: 0.9;
    letter-spacing: 0;

  }
  
  .enroll-button {
    display: inline-block;
    background: #ff6600;
    color: white;
    padding: 10px 21px;
    border-radius: 12px;
    font-size: 16px;
    font-weight: 500;
    text-decoration: none;
    letter-spacing: 0;
    transition: 0.3s ease-in-out;
  }
  
  .enroll-button:hover {
    background: #e05500;
  }
  </style>
  