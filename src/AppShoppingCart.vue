<script setup>
import { ref } from 'vue'
import ShoppingCart from './components/ShoppingCart.vue'

let isOpen = ref(false)

function toggleShoppingCart() {
  isOpen.value = !isOpen.value
}
</script>

<template>
  <header>
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
      <ul>
        <li>
          <a href="#" @click.prevent="toggleShoppingCart">Cart</a>
          <div class="shopping-cart-dropdown-container" v-show="isOpen">
            <ShoppingCart />
          </div>
        </li>
      </ul>
    </nav>
  </header>
  <div class="container main-content">
    Lorem, ipsum dolor sit amet consectetur adipisicing elit. Nemo molestias
    minima impedit vel fuga minus natus quod architecto magni voluptates atque
    consequuntur ea eum, provident, quidem facilis, porro excepturi veritatis
    quibusdam. Inventore harum impedit magni minus quia laudantium obcaecati
    necessitatibus molestiae dolores fugiat sapiente eveniet, culpa a,
    aspernatur saepe non quisquam enim temporibus! Omnis dolorem, nobis
    distinctio consequuntur rem corporis.
    <ShoppingCart />
  </div>
</template>

<style>
.shopping-cart-dropdown-container {
  margin-top: 12px;
  position: absolute;
  right: 0;
  background: white;
  border: 1px solid lightgray;
  border-radius: 5px;
  width: 320px;
  color: #222;
  background: white;
  z-index: 999;
}

.container {
  font-family: sans-serif;
  max-width: 900px;
  margin: 20px auto;
  padding: 0 20px;
}

header {
  font-family: sans-serif;
  background: darkblue;
  color: white;
  padding: 20px 50px;
}

nav {
  display: flex;
  justify-content: space-between;
}

nav > ul {
  display: flex;
  gap: 16px;
  position: relative;
}

nav ul a {
  color: white;
  text-decoration: none;
}
</style>
