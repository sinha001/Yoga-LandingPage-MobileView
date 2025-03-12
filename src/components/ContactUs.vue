<template>
    <section class="contact-section">
      <div class="container text-center position-relative">
        <div class="image-wrapper">
          <!-- Rotating Background Image -->
          <img src="../assets/Images/Group.png" alt="Rotating Lotus" class="rotating-image" />
  
          <!-- Centered Logo -->
          <img src="../assets/Images/image 4.png" alt="Yoga School Logo" class="center-logo" />
        </div>
  
        <!-- Heading -->
        <h2 class="contact-title">Let's Connect and Flow Together!</h2>
  
        <!-- Subtitle -->
        <p class="contact-subtitle">
          Let’s take the first step toward transformation together.
        </p>
  
        <!-- Contact Button -->
        <a href="tel:+1234567890" class="contact-button">
          <i class="bi bi-telephone-fill"></i> Contact us
        </a>
      </div>
    </section>
  </template>
  
  <style scoped>
  .contact-section {
    padding: 48px 24px;
    text-align: center;
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
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
    width: 200px;
    height: 200px;
    position: absolute;
    animation: rotateAnimation 30s linear infinite;
  }
  
  .center-logo {
    width: 111.46px;
    height: 111.46px;
    position: relative;
    z-index: 1; 
  }
  
  @keyframes rotateAnimation {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(360deg);
    }
  }
  
  .contact-title {
    font-size: 28px;
    color: #734875;
    font-weight: 500;
    margin-top: 54px;
    margin-bottom: 12px;
  }
  
  .contact-subtitle {
    font-size: 16px;
    color: #666;
    margin-bottom: 24px;
  }
  
  .contact-button {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: transparent;
    border: 2px solid #734875;
    color: #734875;
    padding: 10px 20px;
    border-radius: 8px;
    font-size: 16px;
    font-weight: 500;
    text-decoration: none;
    transition: all 0.3s ease-in-out;
  }
  
  .contact-button i {
    font-size: 18px;
  }
  
  .contact-button:hover {
    background: #734875;
    color: white;
  }
  </style>
  