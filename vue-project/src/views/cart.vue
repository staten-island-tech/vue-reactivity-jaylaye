<template>
  <div class="cart">
    <h2>Cart</h2>
    <div v-if="selectedSkins.length === 0">Your cart is empty</div>
    <div v-else>
      <div v-for="(skin, index) in selectedSkins" :key="index" class="cart-item">
        <img :src="skin.displayIcon" alt="Gun Skin Image">
        <h3>{{ skin.displayName }}</h3>
        <p>Quantity: {{ skin.quantity }}</p>
        <button @click="removeFromCart(index)">Remove</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    selectedSkins: {
      type: Array,
      default: () => []
    }
  },
  methods: {
    removeFromCart(index) {
      this.$emit('remove-from-cart', index);
    }
  }
}
</script>

