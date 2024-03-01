

<template>

   <h1>Valorant Gun Skin Shop</h1>
  <div id="app">
 
    <div id="buttons">
      <button @click="filterByGun('all')">All</button>
      <button @click="filterByGun('Classic')">Classic</button>
      <button @click="filterByGun('Shorty')">Shorty</button>
      <button @click="filterByGun('Frenzy')">Frenzy</button>
      <button @click="filterByGun('Ghost')">Ghost</button>
      <button @click="filterByGun('Sheriff')">Sheriff</button>
      <button @click="filterByGun('Stinger')">Stinger</button>
      <button @click="filterByGun('Spectre')">Spectre</button>
      <button @click="filterByGun('Bucky')">Bucky</button>
      <button @click="filterByGun('Judge')">Judge</button>
      <button @click="filterByGun('Bulldog')">Bulldog</button>
      <button @click="filterByGun('Guardian')">Guardian</button>
      <button @click="filterByGun('Phantom')">Phantom</button>
      <button @click="filterByGun('Vandal')">Vandal</button>
      <button @click="filterByGun('Ares')">Ares</button>
      <button @click="filterByGun('Odin')">Odin</button>

  
    </div>
    <div class="skin-cards">
      <div v-for="skin in filteredSkins" :key="skin.uuid" class="card">
        <img :src="skin.displayIcon" alt="Gun Skin Image">
        <h3>{{ skin.displayName }}</h3>
        <button @click="addToCart(skin)">Add to Cart</button> 
      </div>
    </div>
    <Cart :selectedSkins="selectedSkins" @remove-from-cart="removeFromCart" />
      </div>
</template>

<script>
import Cart from './views/cart.vue'
export default {
  name: 'App',
  components: {
    Cart
  },

  data() {
    return {
      skins: [],
      filteredSkins: [],
      selectedSkins: []
    };
  },
  methods: {
    async fetchData() {
      try {
        const response = await fetch("https://valorant-api.com/v1/weapons/skins");
        const data = await response.json();
        this.skins = data.data;
        this.filteredSkins = this.skins;
      } catch (error) {
        console.error('Error fetching data:', error);
      }
    },
    filterByGun(gunName) {
  if (gunName.toLowerCase() === 'all') {
    this.filteredSkins = this.skins;
  } else {
    this.filteredSkins = this.skins.filter(skin => skin.displayName.toLowerCase().includes(gunName.toLowerCase()));
  }
    },
    addToCart(skin) {
      const existingSkinIndex = this.selectedSkins.findIndex(item => item.uuid === skin.uuid);
    if (existingSkinIndex !== -1) {
      this.selectedSkins[existingSkinIndex].quantity++;
    } else {
      this.selectedSkins.push({ ...skin, quantity: 1 });
    }
    },
    removeFromCart(index) {
      this.selectedSkins.splice(index, 1);
    }
  },
  mounted() {
    this.fetchData();
  }
}
</script>