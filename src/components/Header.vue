<template>
    <header class="app-header">
        <div class="logo">Vue3 SCART</div>
        <nav class="nav">
        <ul class="nav-list">
            <li class="nav-item">Home</li>
            <li class="nav-item">About</li>
            <li class="nav-item">Services</li>
            <li class="nav-item">Contact</li>
        </ul>
        </nav>
    </header>
</template>
  
  <script>
  export default {
    name: 'AppHeader'
  }
  </script>
  
  <style scoped>
  .app-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    background-color: #333;
    color: white;
  }
  
  .logo {
    font-size: 1.5rem;
  }
  
  .nav {
    display: none;
  }
  
  @media (min-width: 768px) {
    .nav {
      display: block;
    }
  }
  
  .nav-list {
    list-style: none;
    display: flex;
    gap: 1rem;
  }
  
  .nav-item {
    cursor: pointer;
  }
  
  @media (max-width: 767px) {
    .nav-list {
      display: none;
    }
  
    .nav.active .nav-list {
      display: flex;
      flex-direction: column;
      position: absolute;
      top: 100%;
      left: 0;
      background-color: #333;
      width: 100%;
      padding: 1rem 2rem;
    }
  }
  </style>
  