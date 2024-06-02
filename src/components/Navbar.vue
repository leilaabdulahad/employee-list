<template>
  <nav class="navbar">
    <div class="navbar-container">
      <div class="navbar-brand">
        <img src="https://vendre.se/thumb/1967/0x68/vendre-optimizers_logo-black.png" alt="Vendre Logo" />
      </div>
      <div class="navbar-toggle" @click="toggleMenu">
        <span></span>
        <span></span>
        <span></span>
      </div>
      <div :class="['navbar-menu', { 'navbar-menu-active': isMenuActive }]">
        <li>
          <a href="#home" @click="toggleMenu">Home</a>
        </li>
        <li>
          <a href="#about" @click="toggleMenu">About</a>
        </li>
        <li>
          <a href="#products" @click="toggleMenu">Products</a>
        </li>
        <li>
          <a href="#contact" @click="toggleMenu">Contact</a>
        </li>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      isMenuActive: false
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuActive = !this.isMenuActive;
    }
  }
}
</script>

<style scoped>


.navbar {
  padding: 15px 30px;
  display: flex;
  justify-content: center;
  align-items: center;
  position: sticky;
  top: 0;
  width: 100%;
  z-index: 1000;
}

img {
  width: 120px;
}

.navbar-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  max-width: 1200px;
}

.navbar-toggle {
  display: none;
  flex-direction: column;
  cursor: pointer;
  position: relative;
  z-index: 1100;
}
.navbar-toggle span {
  height: 3px;
  width: 25px;
  background: #000;
  margin: 4px 0;
  /* transition: transform 0.3s ease; */
}
.navbar-menu {
  display: flex;
  flex-direction: row;
  justify-content: center;
  list-style: none;
  border-radius: 10px;
}

.navbar-menu li {
  display: flex;
  text-align: center;
}

.navbar-menu a {
  color: #000;
  text-decoration: none;
  font-size: 1.1rem;
  transition: color 0.3s ease, transform 0.3s ease;
  padding: 10px;
  position: relative;
}

.navbar-menu a::after {
  content: '';
  position: absolute;
  width: 100%;
  transform: scaleX(0);
  height: 2px;
  bottom: 0;
  left: 0;
  background-color: #6c6b6b;
  transform-origin: bottom right;
  transition: transform 0.65s ease-out;
}

.navbar-menu a:hover::after {
  transform: scaleX(1);
  transform-origin: bottom left;
}

@media (max-width: 768px) {
  .navbar-container {
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  .navbar-toggle {
    display: flex;
  }

  .navbar-menu {
    flex-direction: column;
    align-items: flex-start;
    position: absolute;
    top: 90px;
    right: 0;
    background-color: #fff;
    width: 100%;
    max-width: 200px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    display: none;
    overflow: hidden;
    max-height: 0;
    transition: max-height 0.3s ease;
    z-index: 1000;
  }

  .navbar-menu-active {
    display: flex;
    max-height: 500px; 
  }

  .navbar-menu li {
    width: 100%;
    margin: 10px 0;
  }

  .navbar-menu a {
    width: 100%;
    padding: 15px;
  }
}
</style>
