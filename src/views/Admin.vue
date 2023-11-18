<template>
    <div class="admin-panel">
      <header>
        <h1>Poultry Management System Admin Panel</h1>
      </header>
  
      <main>
        <nav>
          <ul>
            <li><router-link to="/users">Users</router-link></li>
            <li><router-link to="/branches">Branches</router-link></li>
            <li><router-link to="/products">Products</router-link></li>
            <li><router-link to="/notifications">Notifications</router-link></li>
          </ul>
        </nav>
  
        <router-view></router-view>
      </main>
    </div>
  </template>
  
  <script>
  export default {
    mounted() {
      // Check if user is logged in and has admin privileges
      if (!this.$store.state.user.isLoggedIn || !this.$store.state.user.isAdmin) {
        this.$router.push('/login');
      }
    },
  };
  </script>
  