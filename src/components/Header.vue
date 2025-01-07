<template>
  <div>
    <input type="checkbox" id="checkbtn" />
    <header>
      <div class="logo">
        <router-link to="/"
          ><img src="../assets/img/Group 157 (1).svg" alt="mos-logo"
        /></router-link>
      </div>

      <div class="quick-links">
        <a class="fontSize16-15em">
          <span class="material-symbols-outlined">lunch_dining</span>美味專區
        </a>
        <a class="fontSize16-15em">
          <span class="material-symbols-outlined">storefront</span>店舖情報
        </a>
      </div>

      <label for="checkbtn" class="menubtn">
        <span class="navbar1"></span>
        <span class="navbar2"></span>
        <span class="navbar3"></span>
      </label>
      <nav>
        <!-- <router-link v-for="item in menuItems" :key="item.path" >
          {{ item.name }}
        </router-link> -->
        <a class="fontSize16-15em">
          <span class="material-symbols-outlined"> lunch_dining </span>美味專區
        </a>
        <a class="fontSize16-15em">
          <span class="material-symbols-outlined"> storefront </span>店舖情報
        </a>
        <a class="fontSize16-15em">
          <span class="material-symbols-outlined"> person </span>會員專區
        </a>
        <a class="fontSize16-15em">
          <span class="material-symbols-outlined"> shopping_cart </span>線上購物
        </a>
        <a class="fontSize16-15em">
          <span class="material-symbols-outlined"> sentiment_satisfied </span
          >企業社會責任
        </a>
        <a class="fontSize16-15em">
          <span class="material-symbols-outlined"> handshake </span>人才招募
        </a>
        <a class="fontSize16-15em">
          <span class="material-symbols-outlined"> work </span>投資人專區
        </a>
        <a class="fontSize16-15em">
          <span class="material-symbols-outlined"> insert_chart </span
          >利害關係人專區
        </a>
      </nav>
    </header>
  </div>
</template>
<script setup>
</script>



<style lang="scss" scoped>
@import "../assets/scss/color.scss";

#checkbtn {
  opacity: 0;
  position: absolute;
  z-index: -2;
}
header {
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  background-color: #fff;
}

.quick-links {
  display: none;
}

.quick-links a {
  display: flex;
  align-items: center;
  text-decoration: none;
  color: $text_color_main;
  margin-right: 10px;
}

.quick-links a:hover {
  color: $red_color;
}
.quick-links a:hover span {
  color: $red_color;
}
.quick-links a span {
  margin: 0 5px 0 0;
}

nav {
  display: flex;
}

nav a {
  display: block;
  display: flex;
  align-items: center;
  text-align: center;
  text-decoration: none;
  color: $text_color_main;
  cursor: pointer;
}

nav a:hover {
  color: $red_color;
}
nav span {
  margin: 0 5px 0 0;
}
nav a:hover span {
  color: $red_color;
}
.material-symbols-outlined {
  color: $text_color_main;
}

@media screen and (max-width: 1095px) {
  #checkbtn:checked ~ header nav {
    left: 0;
  }
  .menubtn {
    width: 40px;
    height: 40px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: absolute;
    right: 10px;
    cursor: pointer;
  }
  .navbar1,
  .navbar2,
  .navbar3 {
    width: 28px;
    height: 2px;
    background-color: $text_color_main;
    transition: all 0.3s ease-in-out;
    position: absolute;
  }

  .navbar1 {
    top: 10px;
  }

  .navbar2 {
    top: 18px;
  }

  .navbar3 {
    top: 26px;
  }

  #checkbtn:checked ~ header label .navbar1 {
    transform: rotate(45deg);
    top: 18px;
  }

  #checkbtn:checked ~ header label .navbar2 {
    opacity: 0;
  }

  #checkbtn:checked ~ header label .navbar3 {
    transform: rotate(-45deg);
    top: 18px;
  }

  .quick-links {
    display: flex;
    margin-right: 3rem;
  }

  nav {
    width: 100%;
    height: calc(100vh - 67px);
    position: absolute;
    left: -100%;
    top: 58px;
    flex-direction: column;
    justify-content: space-around;
    transition: 2s;
    background-color: #fff;
    z-index: 9999;
  }
  nav a {
    justify-content: center;
  }
}
@media screen and (min-width: 1096px) {
  .menubtn {
    display: none;
  }

  nav {
    flex-wrap: wrap;
    justify-content: center;
    align-content: center;
  }

  nav a {
    margin: 0 10px;
    // font-size: 20px;
  }
}
</style>
