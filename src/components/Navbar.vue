<template>
    <nav class="navbar">
      <div class="navbar-container">
        <div class="navbar-brand">
          <img src="https://vendre.se/thumb/1967/0x68/vendre-optimizers_logo-black.png" alt="Vendre Logo" />
        </div>
        <div class="navbar-menu">
          <a href="#home">Home</a>
          <a href="#about">About</a>
          <a href="#products">Products</a>
          <a href="#contact">Contact</a>
        </div>
      </div>
    </nav>
  </template>
  
  <script>
  export default {
    name: 'Navbar'
  }
  </script>
  
  <style scoped>
  .navbar {
    color: #000000;
    padding: 10px 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    position: sticky;
    width: 100%;
    transition: background-color 0.3s ease;
  }
  
  img {
    width: 110px;
  }
  
  .navbar-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    max-width: 1200px;
  }
  
  a {
    margin-right: 10px;
  }
  
  .navbar-menu {
    display: flex;
  }
  
  .navbar-menu a {
    color: #000000;
    text-decoration: none;
    font-size: 1rem;
    transition: color 0.3s ease;
    padding: 10px;
  }
  
  .navbar-menu a:hover {
    color: #575757;
  }
  </style>