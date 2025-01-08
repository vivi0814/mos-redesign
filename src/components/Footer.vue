<template>
  <footer class="footer">
    <!-- 左側 Logo -->
    <div class="footer-left">
      <img
        src="/assets/img/Group 157 (1).svg"
        alt="Logo"
        class="footer-logo"
      />
    </div>

    <!-- 中間資訊 -->
    <div class="footer-center">
      <ul class="footer-links">
        <li><a href="#">廠商專區</a></li>
        <li><a href="#">網站使用須知</a></li>
        <li><a href="#">隱私權聲明</a></li>
        <!-- <li></li> -->
      </ul>
      <p>客服專線：0800-208-128</p>
      <p>106台北市大安區仁愛路三段136號2樓201室</p>
      <p>© 2016 MOS Food Services, INC. All rights reserved.</p>
    </div>

    <!-- 右側社群平台 Icon -->
    <div class="footer-right">
      <a href="#" class="social-icon">
        <img src="/assets/img/instagram.png" alt="instagram" />
      </a>
      <a href="#" class="social-icon">
        <img src="/assets/img/youtube.png" alt="youtube" />
      </a>
      <a href="#" class="social-icon">
        <img src="/assets/img/twitter.png" alt="twitter" />
      </a>
      <a href="#" class="social-icon">
        <img src="/assets/img/facebook.png" alt="facebook" />
      </a>
    </div>
  </footer>
</template>

<script setup>
</script>

<style lang="scss" scoped>
@import "../assets/scss/color.scss";

.footer {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 20px 10px 5px 10px;
  background-color: #fff;
  color: $text_color_main;
}

.footer-left {
  flex: 1;
  margin: auto;
  display: flex;
  justify-content: center;
}

.footer-logo {
  width: 100px;
}

.footer-center {
  flex: 2;
  text-align: center;
}

.footer-links {
  list-style: none;
  padding: 0;
  margin-bottom: 10px;
}

.footer-links li {
  display: inline;
  margin-right: 15px;
}

.footer-links a {
  color: $text_color_main;
  text-decoration: none;
}

.footer-right {
  flex: 1;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.social-icon {
  margin-left: 10px;
}

@media (max-width: 768px) {
  .footer {
    flex-direction: column;
    align-items: center;
  }

  .footer-left,
  .footer-center,
  .footer-right {
    text-align: center;
    margin-bottom: 10px;
  }
}
</style>
