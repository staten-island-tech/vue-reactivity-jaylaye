<template>
  <main>
    <div class="skin-cards">
      <div v-for="(card, index) in skinCards" :key="index" class="card">
        <img :src="card.displayIcon" alt="Skin Image">
        <h3>{{ card.displayName }}</h3>
      </div>
    </div>
  </main>
</template>


<script setup>



const URL = "https://valorant-api.com/v1/weapons/skins";
const skinCards = ref([]);

async function getData(URL) {
  try {
    const response = await fetch(URL);
    const data = await response.json();
    const skinList = data.data;

  for (const skin of skinList){
   const skinInfo = await fetchskinInfo(skin.uuid);
   createCard(skinInfo);
  }

  console.log(data);
  } catch (error) {
    console.error(error); 
  }
}

async function getSkinInfo(skinUuid) {
  const skinInfoURL = `https://valorant-api.com/v1/weapons/skins/${skinUuid}`
  const response = await fetch(skinInfoURL);
  const skinInfo = await response.json();
  return skinInfo.data;
}
function createCard(skinInfo) {
  const card = {
    imgSrc: skinInfo.displayIcon,
    displayName: skinInfo.displayName
  };
  skinCards.value.push(card);
}

getData(URL);   

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Caveat:wght@400..700&family=Rock+3D&family=Rubik+Glitch+Pop&display=swap')
</style>
