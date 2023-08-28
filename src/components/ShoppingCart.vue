<template>
    <div class="shopping-cart">
      <div class="cart-item" v-for="item in cartItems" :key="item.id">
        <img :src="item.image" alt="Item" class="item-image" />
        <div class="item-details">
          <h3>{{ item.title }}</h3>
          <p>Price: ${{ item.price }}</p>
          <button @click="removeFromCart(item.id)">Remove from Cart</button>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  
  const cartItems = ref([]);
  
  const removeFromCart = (itemId) => {
    cartItems.value = cartItems.value.filter(item => item.id !== itemId);
  };
  
  onMounted(async () => {
    const response = await fetch('https://jsonplaceholder.typicode.com/photos?_limit=5');
    const data = await response.json();
    cartItems.value = data.map(item => ({
      id: item.id,
      title: item.title,
      price: (Math.random() * 100).toFixed(2),
      image: item.thumbnailUrl
    }));
  });
  </script>
  
  <style scoped>
  .shopping-cart {
    width: 90%;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    margin: 20px auto;
    gap: 1rem;
  }

  .cart-item {
    width: 100%;
    max-width: 400px;
    border: 1px solid #ccc;
    padding: 1rem;
    display: flex;
    align-items: center;
    gap: 1rem;
    transition: border-color 0.3s, box-shadow 0.3s;
  }
  
  .cart-item:hover{
    border-color: #333;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }
  
  .item-image {
    max-width: 100px;
    max-height: 100px;
  }
  
  .item-details {
    flex: 1;
  }
  </style>
  