<template>
  <header id="top-header">
        <div class="flex">
          <h1 class="header-logo">estra inc.</h1>
          <nav class="header-nav">
            <ul>
              <li><a href="#">home</a></li>
              <li><a href="#">about</a></li>
              <li><a href="#">service</a></li>
              <li><a href="#">works</a></li>
              <li><a href="#">price</a></li>
              <li><a href="#">contact</a></li>
            </ul>
          </nav>
        </div>
        <div id="hamburger" @click="hamburger" :class="{'active': isClass}">
          <span></span>
          <span></span>
          <span></span>
        </div>
        <nav class="menu" :class="{'open': isClass}">
          <h2>estra inc.</h2>
          <ul class="menu-content">
            <li><a href="#">home</a></li>
            <li><a href="#">about</a></li>
            <li><a href="#">service</a></li>
            <li><a href="#">works</a></li>
            <li><a href="#">price</a></li>
            <li><a href="#">contact</a></li>
          </ul>
        </nav>
      </header>
</template>
<script>
export default {
  data(){
    return{
      isClass: false,
    }
  },
  methods: {
    hamburger() {
      this.isClass = !this.isClass
    }
  }
}
</script>
<style scoped>

/*------------------------*/
/*         header         */
/*------------------------*/
a {
  color: #333333;
  text-decoration: none;
}
.flex {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}
#top-header {
  height: 70px;
  line-height: 70px;
  background: rgba(0, 0, 0, 1);
}

.header-logo {
  font-size: 20px;
  font-weight: bold;
  margin-left: 35px;
  color: #fff;
  line-height: 70px;
}

.header-nav li {
  display: inline-block;
  margin-right: 35px;
  font-size: 16px;
}

.header-nav a {
  color: #fff;
}
.menu{
  position: fixed;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100vh;
  background-color: rgb(14, 60, 145);
  z-index: 999;
  text-align: center;
  transition: 0.5s;
}
.menu h2{
  color: white;
  font-size: 20px;
}
.menu-content li{
  padding: 0;
  margin: 15px;
}
.menu-content a{
  color: white;
  font-size: 20px;
}

@media screen and (max-width:480px){
  .header-nav{
    display: none;
  }
  #hamburger{
    z-index: 1000;
    display: flex;
    position: absolute;
    top: 13px;
    right: 10px;
    width: 40px;
    height: 40px;
    cursor: pointer;
    text-align: center;

  }
  #hamburger span{
    display: block;
    position: absolute;
    width: 30px;
    height: 2px;
    left: 4px;
    background-color: white;
    transition: 0.6s;
  }
  #hamburger span:nth-child(1){
    top: 10px;
  }
  #hamburger span:nth-child(2){
    top: 20px;
  }
  #hamburger span:nth-child(3){
    top: 30px;
  }
  .header-logo{
    margin: 0 auto;
  }
  #hamburger.active span:nth-child(1){
    top: 20px;
    transform: rotate(45deg);
  }
  #hamburger.active span:nth-child(2){
    opacity: 0;
  }
  #hamburger.active span:nth-child(3){
    top: 20px;
    transform: rotate(-45deg);
  }
  .menu.open{
    left: 0;
  }
}
</style>