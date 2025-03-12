<template>
  <!-- Just an image -->
  <nav class="navbar navbar-expand-lg  ">
    <a class="navbar-brand" href="#">
      <img src="../assets/Images/logo.png" width="72" height="72" alt="">
    </a>
    <div class="menu" id="navbarNav">
      <ul class="navbar-nav d-flex align-items-center">
        <li class="nav-item d-flex align-items-center">
          <a class="nav-link" href="#">Get a Virtual Tour</a>
          <img src="../assets/Images/fluent_chat-video-20-filled.png" width="28" height="28" alt="">
        </li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  padding: 20px 24px 20px 24px;
  border-bottom: 1px solid #734875;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 2;
  background-color: #FFFFFF;

}
.nav-link{
  color: #734875;
  font-size: 14px;
  font-weight: 540;
  text-decoration: underline;
  gap: 4px;
  font-family: "roboto";
}

.menu {
  display: flex;
  align-items: center;
  gap: 8px; 
}

.nav-item{
  list-style-type: none;
}
</style>
