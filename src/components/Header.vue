<template>
  <header>
    <h1>Meet the staff at 
      <a href="https://vendre.se" target="_blank" rel="noopener noreferrer">
        Vendre
      </a>
    </h1>
    <p>The people that make it happen </p>

    <div class="star-container">
      <button class="intern-btn" @click="showModal = true">New intern?</button>
      <div class="star" v-for="i in 5" :key="i"></div>
    </div>

    <div v-if="showModal" class="modal" @click.self="closeModal">
      <div class="modal-content">
        <span @click="closeModal" class="close">&times;</span>
        <div class="modal-info">
          <img class="profile-pic" src="./assets/profile-img.jpg" alt="Internship Image">
          <div class="modal-details">
            <h2 class="modal-h1">Leila Abdulahad</h2>
            <a class="email" href="mailto:leilaabdulahad@hotmail.com">leilaabdulahad@hotmail.com</a>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>


  
  <script>
  export default {
    name: 'Header',
    data() {
      return {
        showModal: false
      }
    },
    methods: {
      closeModal() {
        this.showModal = false;
      }
    }
  }
  </script>
  
  <style scoped>
  header {
    color: #000000;
    padding: 40px 0;
    text-align: center;
    width: 100%;
    margin: 0;
    padding: 0;
    position: relative;
    overflow: hidden;
    margin-top: 20px;
  }
  
  header h1 {
    font-size: 3rem;
    margin: 50px 0 5px 0;
    animation: slideIn 1s ease-out forwards;
  }
  
  header a {
    color: #000000;
    text-decoration: none;
    transition: color 0.3s ease;
  }
  
  header a:hover {
    color: #747474;
  }
  
  header p {
    font-size: 1.5rem;
    margin-bottom: 40px;
    animation: fadeIn 1s ease-out forwards;
  }
  
  button {
    background-color: #000000;
    color: #ffffff;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    font-size: 1rem;
    cursor: pointer;
    animation: fadeInUp 1s ease-out forwards;
    margin-bottom: 40px;
  }
  
  .modal {
    position: fixed;
    z-index: 1;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0, 0, 0, 0.4);
  }

  .modal-info {
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal-details {
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin:0;
}

.modal-h1 {
  margin: 0;
}

.email {
  color: black;
  margin-top: 5px;
}

.modal-content {
    background-color: #fefefe;
    margin: 15% auto;
    padding: 20px;
    border: 1px solid #888;
    max-width: 400px;
    color: #000;
    border-radius: 10px;
    animation: zoomIn 0.5s ease-out forwards;
}
  
.close {
    color: #aaa;
    float: right;
    font-size: 28px;
    font-weight: bold;
    animation: fadeIn 1s ease-out forwards;
}
  
.close:hover,
.close:focus {
    color: black;
    text-decoration: none;
    cursor: pointer;
}

  .intern-btn{
    background-color: #254336;
  }
  .intern-btn:hover{
    background-color: #475f53;
  }
  
  @keyframes slideIn {
    from {
      transform: translateY(-50px);
      opacity: 0;
    }
    to {
      transform: translateY(0);
      opacity: 1;
    }
  }
  
  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
  
  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  @keyframes zoomIn {
    from {
      transform: scale(0.8);
    }
    to {
      transform: scale(1);
    }
  }

  </style>  