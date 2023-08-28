<template>
    <footer class="footer">
      <div class="footer-content">
        <div class="logo">Vue3</div>
        <nav class="footer-nav">
          <ul class="nav-list">
            <li class="nav-item">Home</li>
            <li class="nav-item">About</li>
            <li class="nav-item">Services</li>
            <li class="nav-item">Contact</li>
          </ul>
        </nav>
      </div>
    </footer>
  </template>
  
  <script>
  export default {
    name: 'AppFooter'
  }
  </script>
  
  <style scoped>
  .footer {
    background-color: #333;
    color: white;
    padding: 2rem;
  }
  
  .footer-content {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
  }
  
  .logo {
    font-size: 1.5rem;
  }
  
  .footer-nav {
    flex: 1;
    text-align: right;
  }
  
  .nav-list {
    list-style: none;
    display: flex;
    gap: 1rem;
    justify-content: flex-end;
  }
  
  .nav-item {
    cursor: pointer;
  }
  
  @media (max-width: 767px) {
    .footer-content {
      flex-direction: column;
      align-items: center;
    }
  
    .footer-nav {
      margin-top: 1rem;
      text-align: center;
    }
  
    .nav-list {
      justify-content: center;
    }
  }
  </style>
  