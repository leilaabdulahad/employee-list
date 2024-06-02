<template>
    <div class="container">
      <div class="employees-list">
        <div v-for="employee in employees" :key="employee.id" class="employee-card">
          <img :src="employee.avatar" alt="Profile Picture" class="profile-pic" />
          <div class="employee-details">
            <h2>{{ employee.first_name }} {{ employee.last_name }}</h2>
            <a :href="'mailto:' + employee.email">{{ employee.email }}</a>
          </div>
        </div>
      </div>
      <div class="pagination">
        <button @click="prevPage" :disabled="currentPage === 1">Previous</button>
        <span>Page {{ currentPage }} of {{ totalPages }}</span>
        <button @click="nextPage" :disabled="currentPage === totalPages">Next</button>
      </div>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        employees: [],
        currentPage: 1,
        totalPages: 1,
      };
    },
    created() {
      this.fetchData();
    },
    methods: {
      async fetchData() {
        const response = await axios.get(`https://reqres.in/api/users?page=${this.currentPage}`);
        this.employees = response.data.data;
        this.totalPages = response.data.total_pages;
      },
      nextPage() {
        if (this.currentPage < this.totalPages) {
          this.currentPage++;
          this.fetchData();
        }
      },
      prevPage() {
        if (this.currentPage > 1) {
          this.currentPage--;
          this.fetchData();
        }
      },
    },
  };
  </script>
  
  
  <style>

body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f5f5f5;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.employees-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
}

.employee-card {
  display: flex;
  align-items: center;
  background-color: #fff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s;
}

.employee-card:hover {
  transform: translateY(-5px);
}

.profile-pic {
  border-radius: 50%;
  width: 70px;
  height: 70px;
  object-fit: cover;
  margin-right: 20px;
}

.employee-details h2 {
  margin: 0;
  font-size: 18px;
  color: #333;
}

.employee-details a {
  color: #000000;
  text-decoration: none;
}

.employee-details a:hover {
  text-decoration: underline;
}

.pagination {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 30px;
}

.pagination button {
  background-color: #254336;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 0 5px;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.pagination button:disabled {
  background-color: #ccc;
  cursor: not-allowed;
}

.pagination button:hover:not(:disabled) {
  background-color: #6B8A7A;
}

.pagination span {
  margin: 0 10px;
}
</style>
