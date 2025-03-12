<template>
    <footer class="footer">
      <div class="container">
        <div class="social-icons">
          <a href="#" class="social-link"><i class="bi bi-facebook"></i></a>
          <a href="#" class="social-link"><i class="bi bi-instagram"></i></a>
          <a href="#" class="social-link"><i class="bi bi-linkedin"></i></a>
          <a href="#" class="social-link"><i class="bi bi-youtube"></i></a>
        </div>
  
        <hr class="footer-line" />
  
        <div class="certifications">
          <img src="../assets/Images/yoga-alliance.png" alt="Yoga Alliance" />
          <img src="../assets/Images/200-rys.png" alt="RYS 200" />
          <img src="../assets/Images/300-rys.png" alt="RYS 300" />
        </div>
  
        <hr class="footer-line" />
  
        <p class="copyright">
          Copyright © 2009-2024 Hari Om Yoga Vidya School ®
        </p>
      </div>
    </footer>
  </template>
  
  <style scoped>
  .footer {
    background-color: #FFF2EB;
    padding: 32px 0;
    text-align: center;
  }
  
  .social-icons {
    display: flex;
    justify-content: center;
    gap: 24px;
    margin-bottom: 16px;
  }
  
  .social-link .bi{
    font-size: 32px;
    color: #734875;
  }
  
  .social-link:hover {
    color: #482c5a;
  }
  
  .footer-line {
    border: none;
    border-top: 1px solid #734875;
    margin: 16px auto;
    width: 90%;
  }
  
  .certifications {
    display: flex;
    justify-content: center;
    gap: 24px;
    margin: 16px 0;
  }
  
  .certifications img {
    width: 64px;
    height: auto;
  }
  
  .copyright {
    font-size: 14px;
    color: #734875;
    margin-top: 16px;
    font-weight: 400;
    letter-spacing: 0;
  }
  </style>
  