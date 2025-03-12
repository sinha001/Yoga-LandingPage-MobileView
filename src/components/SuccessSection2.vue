<template>
    <section class="hero-section">
      <div class="container">
        <div class="hero-content">
          <p class="hero-tagline">FLOW INTO YOUR FUTURE</p>
          <h1 class="hero-title">Turn Your Passion <br> into Purpose</h1>
          <p class="hero-description">
            Transform your practice into a meaningful career with our Yoga Teacher Training Course 
            and inspire others on their journey to wellness.
          </p>
  
          <div class="hero-buttons">
            <a href="#" class="apply-button">Apply Now</a>
            <a href="#" class="syllabus-button">
              <i class="bi bi-download"></i> Download Syllabus
            </a>
          </div>
        </div>
  
        <!-- Rotating Background Image & Centered Logo -->
        <div class="image-wrapper">
          <img src="../assets/Images/Group (1).png" alt="Rotating Lotus" class="rotating-image" />
          <img src="../assets/Images/Vector (1).png" alt="Yoga School Logo" class="center-logo" />
        </div>
      </div>
    </section>
  </template>
  
  <style scoped>
  .hero-section {
    background-color: #734875;
    color: white;
    padding: 48px 19px;
    position: relative;
    text-align: left;
    overflow: hidden;
    display: flex;
    min-height: 361px;
    justify-content: center;
  }
  
  .container {
    position: relative;
    z-index: 1;
  }
  
  /* Image Wrapper (Top-Right Corner) */
  .image-wrapper {
    position: absolute;
    top: -25%;
    right: -20%;
    width: 200px;
    height: 200px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  /* Rotating Background Image (Only Partial Rotation) */
  .rotating-image {
    width: 180px;
    position: absolute;
    animation: partialRotate 5s ease-in infinite normal;
    opacity: 0.5;
  }
  
  /* Centered Logo (Stable & Aligned) */
  .center-logo {
    width: 80px;
    position: absolute;
    z-index: 2;
    opacity: 0.5;
  }
  
  /* Limited Rotation Animation */
  @keyframes partialRotate {
    0% {
      transform: rotate(-10deg);
    }
    100% {
      transform: rotate(20deg);
    }
  }
  
  .hero-content {
    max-width: 500px;
  }
  
  .hero-tagline {
    text-transform: uppercase;
    font-size: 14px;
    letter-spacing: 1px;
    font-weight: 400;
    opacity: 0.8;
  }
  
  .hero-title {
    font-size: 36px;
    font-weight: 400;
    line-height: 1.2;
    letter-spacing: -1px;
    margin: 12px 0;
  }
  
  .hero-description {
    font-size: 16px;
    line-height: 1.6;
    opacity: 0.9;
    letter-spacing: 0;
    margin: 24px 0;
    color: #ffffffd9 !important;
  }
  
  .hero-buttons {
    display: flex;
    gap: 12px;
    width: 335px;
    height: 40px;
  }
  
  /* ✅ Fix for "Apply Now" Button Text Centering */
  .apply-button {
    background: #ff6600;
    color: white;
    border-radius: 12px;
    font-size: 14px;
    font-weight: 400;
    width: 182px;
    height: 40px;
    text-align: center;
    text-decoration: none;
    transition: background 0.3s ease-in-out;
    letter-spacing: -0.5px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  
  .apply-button:hover {
    background: #e05500;
  }
  
  /* ✅ Fix for "Download Syllabus" Button */
  .syllabus-button {
    background: transparent;
    color: white;
    border: 2px solid white;
    border-radius: 8px;
    font-size: 14px;
    font-weight: 400;
    width: 182px;
    height: 40px;
    letter-spacing: -0.8px;
    text-decoration: none;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    transition: background 0.3s ease-in-out;
  }
  
  .syllabus-button i {
    font-size: 18px;
  }
  
  .syllabus-button:hover {
    background: rgba(255, 255, 255, 0.2);
  }
  </style>
  