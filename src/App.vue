<template>
  <div>
    <div class="navbar">
      <router-link class="nav-link" to="/location">Location</router-link>
      <router-link class="nav-link" to="/">Home</router-link>
    </div>
    
    <router-view />
  </div>
</template>

<style scoped>
.navbar {
  text-align: center;
  margin: 5rem;
}

.nav-link {
  text-decoration: none;
  margin: 0 1rem;
  padding: 0.5rem 1rem;
  font-size: 50px;
  color: white;
  background-color: #ebe480;
  border-radius: 5px; 
  transition: all 0.3s ease; 
}

.nav-link:hover {
  background-color: #6b7132; 
}
</style>
