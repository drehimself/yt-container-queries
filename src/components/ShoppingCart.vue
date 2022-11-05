<script setup>
import { computed, ref } from 'vue'

const items = ref([
  {
    id: 1,
    name: 'MacBook Pro',
    description: 'Description for MacBook Pro.',
    image: new URL('../assets/macbookpro.jpg', import.meta.url).href,
    price: 349999,
    quantity: 1,
  },
  {
    id: 2,
    name: 'Mac Studio',
    description: 'Description for Mac Studio.',
    image: new URL('../assets/macstudio.jpg', import.meta.url).href,
    price: 399999,
    quantity: 1,
  },
  {
    id: 3,
    name: 'iPhone Pro',
    description: 'Description for iPhone Pro.',
    image: new URL('../assets/iphonepro.jpg', import.meta.url).href,
    price: 99999,
    quantity: 1,
  },
  {
    id: 4,
    name: 'iPad Pro',
    description: 'Description for iPad Pro.',
    image: new URL('../assets/ipadpro.jpg', import.meta.url).href,
    price: 129999,
    quantity: 1,
  },
])

function updateQuantity(event, item) {
  item.quantity = parseInt(event.target.value)
}

function deleteItem(id) {
  items.value = items.value.filter(item => item.id !== id)
}

const numberOfItems = computed(() => {
  return items.value.reduce((prev, curr) => prev + curr.quantity, 0)
})

const subtotal = computed(() => {
  return items.value.reduce(
    (prev, curr) => prev + curr.quantity * curr.price,
    0
  )
})

const tax = computed(() => {
  return Math.round(subtotal.value * 0.13)
})

const total = computed(() => {
  return subtotal.value + tax.value
})
</script>

<template>
  <div v-if="items.length > 0" class="shopping-cart-container">
    <div class="cart-items-container">
      <div v-for="item in items" :key="item.id" class="cart-item">
        <div class="cart-item-left">
          <div class="cart-item-image">
            <img
              :src="item.image"
              class="cart-item-image"
              alt="item
                image"
            />
          </div>
          <div class="cart-item-details">
            <div class="cart-item-name">{{ item.name }}</div>
            <div class="cart-item-description">{{ item.description }}</div>
          </div>
        </div>
        <div class="cart-item-right">
          <div class="cart-item-quantity">
            <input
              @change="updateQuantity($event, item)"
              type="number"
              value="1"
              min="1"
              max="10"
            />
          </div>
          <div class="cart-item-total">${{ item.price / 100 }}</div>
          <div class="cart-item-remove">
            <button @click="deleteItem(item.id)">&times;</button>
          </div>
        </div>
      </div>
    </div>
    <div class="cart-totals-container">
      <div class="cart-total-labels">
        <div># of Items</div>
        <div>Subtotal</div>
        <div>Tax (13%)</div>
        <div class="cart-total">Total</div>
      </div>
      <div class="cart-total-values">
        <div>{{ numberOfItems }}</div>
        <div>${{ subtotal / 100 }}</div>
        <div>${{ tax / 100 }}</div>
        <div class="cart-total">${{ total / 100 }}</div>
      </div>
    </div>
  </div>

  <div v-else class="shopping-cart-container">
    There are no items in your cart.
  </div>
</template>

<style scoped>
.shopping-cart-container {
  margin: 20px 0;
}

.cart-item {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  border-top: 1px solid lightgray;
  padding: 10px 0;
}

.cart-item:last-child {
  border-bottom: 1px solid lightgray;
}

.cart-item-left {
  display: flex;
}

.cart-item-right {
  display: flex;
  align-items: center;
  padding: 12px 0;
}

.cart-item-image {
  display: none;
  width: 70px;
  height: 70px;
}

.cart-item-details {
  padding: 0 10px;
}

.cart-item-description {
  margin-top: 10px;
  color: gray;
  line-height: 1.2;
  font-size: 14px;
}

.cart-item-quantity,
.cart-item-total {
  width: 20px;
  padding: 0 22px;
}

.cart-item-remove {
  padding-left: 40px;
}

.cart-item-remove > button {
  font-size: 18px;
}

.cart-totals-container {
  display: grid;
  justify-content: end;
  grid-template-columns: 120px 120px;
  text-align: right;
  line-height: 2.2;
  margin: 20px 0;
  padding: 10px;
}

.cart-total-labels {
  text-transform: uppercase;
  color: gray;
}

.cart-total {
  font-weight: bold;
}

@container (min-width: 500px) {
  .cart-item {
    padding: 20px 0;
  }
  .cart-item-image {
    display: block;
  }

  .cart-item-quantity,
  .cart-item-total {
    width: 36px;
    padding: 0 30px;
  }

  .cart-item {
    flex-direction: row;
    justify-content: space-between;
    padding: 20px 0;
  }

  .cart-item-right {
    padding: 0;
  }
}
</style>
