<template>
   <h1>Gun Skin Shop</h1>
  <div id="app">
 
    <div id="buttons">
      <button @click="filterByCategory('all')">All</button>
      <button @click="filterByCategory('Classic')">Shorty</button>
      <button @click="filterByCategory('Shorty')">Shorty</button>
      <button @click="filterByCategory('Frenzy')">Frenzy</button>
      <button @click="filterByCategory('Ghost')">Ghost</button>
      <button @click="filterByCategory('Sheriff')">Sheriff</button>
      <button @click="filterByCategory('Stinger')">Stinger</button>
      <button @click="filterByCategory('Spectre')">Spectre</button>
      <button @click="filterByCategory('Bucky')">Bucky</button>
      <button @click="filterByCategory('Judge')">Judge</button>
      <button @click="filterByCategory('Bulldog')">Bulldog</button>
      <button @click="filterByCategory('Guardian')">Guardian</button>
      <button @click="filterByCategory('Phantom')">Phantom</button>
      <button @click="filterByCategory('Vandal')">Vandal</button>
      <button @click="filterByCategory('Ares')">Ares</button>
      <button @click="filterByCategory('Odin')">Odin</button>
    </div>
      </div>
</template>

<script>
export default {
  name: 'App',
  methods: {
    filterByCategory(category) {
      // Implement your filtering logic here
      console.log(`Filtering by category: ${category}`);
    }
  }
}
</script>


