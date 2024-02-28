<script setup>

const URL = "https://valorant-api.com/v1/weapons/skins";

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
 getData(URL);     

</script>

<template>
  <main>
   

  </main>

</template>
