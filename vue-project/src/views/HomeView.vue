<script setup>

const URL = "https://valorant-api.com/v1/weapons/skins";

async function getData(URL) {
  try {
    const response = await fetch(URL);
    const data = await response.json();
    const skinList = data.results;

   for (const pokemon of pokemonList){
      const pokemonDetails = await fetchPokemonDetails(pokemon.name);
      createCard(pokemonDetails);
    }
  
   
    console.log(data);
  } catch (error) {
    console.error(error);
  }
};

/* const skins = [

        //side arms

    //frenzys
            {
              "name": "Origin",
              "gun": "Frenzy",
              "tier": "Standard",
              "image": "https://valorantinfo.com/images/us/origin-frenzy-level-4variant-3-white_valorant_full_skin_154554.webp",
            },


            {
              "name": "BlastX",
              "gun": "Frenzy",
              "tier": "Standard",
              "image": "https://vgraphs.com/images/weapons/skins/full-details/valorant-blastx-frenzy-weapon-skin.png",
            },

            {
              "name": "Glitchpop",
              "gun": "Frenzy",
              "tier": "Standard",
              "image": "https://vgraphs.com/images/weapons/skins/full-details/valorant-blastx-frenzy-weapon-skin.png",
            },
            {
              "name": "RGX 2.0",
              "gun": "Frenzy",
              "tier": "Standard"
            },
            {
              "name": "Horizon",
              "gun": "Frenzy",
              "tier": "Standard"
            },
            {
              "name": "Sakura",
              "gun": "Frenzy",
              "tier": "Standard"
            },
            {
              "name": "Prelude to Chaos",
              "gun": "Frenzy",
              "tier": "Standard"
            },
            {
              "name": "Gaia",
              "gun": "Frenzy",
              "tier": "Standard"
            },
            {
              "name": "Elderflame",
              "gun": "Frenzy",
              "tier": "Standard"
            },
            {
              "name": "Sovereign",
              "gun": "Frenzy",
              "tier": "Standard"
            },
            {
              "name": "RGX 11z Pro",
              "gun": "Frenzy",
              "tier": "Standard"
            },
            {
              "name": "Reaver",
              "gun": "Frenzy",
              "tier": "Standard"
            },
         
            //shorty


                {
                  "name": "Protocol",
                  "gun": "Shorty",
                  "tier": "Standard"
                },
                {
                  "name": "BlastX",
                  "gun": "Shorty",
                  "tier": "Standard"
                },
                {
                  "name": "Champions 2023",
                  "gun": "Shorty",
                  "tier": "Standard"
                },
                {
                  "name": "Sakura",
                  "gun": "Shorty",
                  "tier": "Standard"
                },
                {
                  "name": "Prelude to Chaos",
                  "gun": "Shorty",
                  "tier": "Standard"
                },
                {
                  "name": "Sovereign",
                  "gun": "Shorty",
                  "tier": "Deluxe"
                },
                {
                  "name": "RGX 11z Pro",
                  "gun": "Shorty",
                  "tier": "Select"
                },
                {
                  "name": "Oni",
                  "gun": "Shorty",
                  "tier": "Deluxe"
                },
                {
                  "name": "Reaver",
                  "gun": "Shorty",
                  "tier": "Exclusive"
                },
                {
                  "name": "Elderflame",
                  "gun": "Shorty",
                  "tier": "Deluxe"
                },
                {
                  "name": "Luxe",
                  "gun": "Shorty",
                  "tier": "Select"
                },
                {
                  "name": "Glitchpop",
                  "gun": "Shorty",
                  "tier": "Select"
                },
                {
                  "name": "Duality",
                  "gun": "Shorty",
                  "tier": "Deluxe"
                },
  
              
        // Sheriff
        {
          "name": "Prime",
          "gun": "Sheriff",
          "tier": "Deluxe"
        },
        {
          "name": "Reaver",
          "gun": "Sheriff",
          "tier": "Exclusive"
        },
        {
          "name": "Glitchpop",
          "gun": "Sheriff",
          "tier": "Select"
        },
        {
          "name": "Duality",
          "gun": "Sheriff",
          "tier": "Deluxe"
        },
        {
          "name": "Sovereign",
          "gun": "Sheriff",
          "tier": "Deluxe"
        },
        {
          "name": "RGX 11z Pro",
          "gun": "Sheriff",
          "tier": "Select"
        },
        {
          "name": "Oni",
          "gun": "Sheriff",
          "tier": "Deluxe"
        },
        {
          "name": "Protocol",
          "gun": "Sheriff",
          "tier": "Standard"
        },
        {
          "name": "BlastX",
          "gun": "Sheriff",
          "tier": "Standard"
        },
        {
          "name": "Champions 2023",
          "gun": "Sheriff",
          "tier": "Standard"
        },
        {
          "name": "Prelude to Chaos",
          "gun": "Sheriff",
          "tier": "Standard"
        },
        {
          "name": "Sakura",
          "gun": "Sheriff",
          "tier": "Standard"
        },
        {
          "name": "Elderflame",
          "gun": "Sheriff",
          "tier": "Deluxe"
        },
        {
          "name": "Luxe",
          "gun": "Sheriff",
          "tier": "Select"
        },
        {
          "name": "Gaia",
          "gun": "Sheriff",
          "tier": "Standard"
        },
        {
          "name": "Nitro",
          "gun": "Sheriff",
          "tier": "Standard"
        },
        {
          "name": "Magepunk",
          "gun": "Sheriff",
          "tier": "Standard"
        },
        {
          "name": "RGX 2.0",
          "gun": "Sheriff",
          "tier": "Select"
        },
        {
          "name": "Glitchpop 2.0",
          "gun": "Sheriff",
          "tier": "Select"
        },
        {
          "name": "Horizon",
          "gun": "Sheriff",
          "tier": "Standard"
        },
      
        // Ghost
        {
          "name": "Sakura",
          "gun": "Ghost",
          "tier": "Standard"
        },
        {
          "name": "Prelude to Chaos",
          "gun": "Ghost",
          "tier": "Standard"
        },
        {
          "name": "Sovereign",
          "gun": "Ghost",
          "tier": "Deluxe"
        },
        {
          "name": "Reaver",
          "gun": "Ghost",
          "tier": "Exclusive"
        },
        {
          "name": "RGX 11z Pro",
          "gun": "Ghost",
          "tier": "Select"
        },
        {
          "name": "Oni",
          "gun": "Ghost",
          "tier": "Deluxe"
        },
        {
          "name": "Protocol",
          "gun": "Ghost",
          "tier": "Standard"
        },
        {
          "name": "BlastX",
          "gun": "Ghost",
          "tier": "Standard"
        },
        {
          "name": "Champions 2023",
          "gun": "Ghost",
          "tier": "Standard"
        },
        {
          "name": "Elderflame",
          "gun": "Ghost",
          "tier": "Deluxe"
        },






        //SMGS

            //stinger

          {
            "name": "RGX 11z Pro",
            "gun": "Stinger",
            "tier": "Select"
          },
          {
            "name": "Glitchpop",
            "gun": "Stinger",
            "tier": "Select"
          },
          {
            "name": "Reaver",
            "gun": "Stinger",
            "tier": "Exclusive"
          },
          {
            "name": "Sovereign",
            "gun": "Stinger",
            "tier": "Deluxe"
          },
          {
            "name": "RGX 2.0",
            "gun": "Stinger",
            "tier": "Select"
          },
          {
            "name": "Horizon",
            "gun": "Stinger",
            "tier": "Standard"
          },
          {
            "name": "Radiant Guardian",
            "gun": "Stinger",
            "tier": "Battle Pass"
          },
          {
            "name": "Champions 2023",
            "gun": "Stinger",
            "tier": "Standard"
          },
          {
            "name": "BlastX",
            "gun": "Stinger",
            "tier": "Standard"
          },
          {
            "name": "Luxe",
            "gun": "Stinger",
            "tier": "Select"
          },
          {
            "name": "Nitro",
            "gun": "Stinger",
            "tier": "Standard"
          },
          {
            "name": "Magepunk",
            "gun": "Stinger",
            "tier": "Standard"
          },
        
          // Spectre
          {
            "name": "Reaver",
            "gun": "Spectre",
            "tier": "Exclusive"
          },
          {
            "name": "Glitchpop",
            "gun": "Spectre",
            "tier": "Select"
          },
          {
            "name": "RGX 11z Pro",
            "gun": "Spectre",
            "tier": "Select"
          },
          {
            "name": "Sovereign",
            "gun": "Spectre",
            "tier": "Deluxe"
          },
          {
            "name": "RGX 2.0",
            "gun": "Spectre",
            "tier": "Select"
          },
          {
            "name": "Horizon",
            "gun": "Spectre",
            "tier": "Standard"
          },
          {
            "name": "Nitro",
            "gun": "Spectre",
            "tier": "Standard"
          },
          {
            "name": "Magepunk",
            "gun": "Spectre",
            "tier": "Standard"
          },
          {
            "name": "BlastX",
            "gun": "Spectre",
            "tier": "Standard"
          },
          {
            "name": "Luxe",
            "gun": "Spectre",
            "tier": "Select"
          },


          

            // Judge
  {
    "name": "Elderflame",
    "gun": "Judge",
    "tier": "Deluxe"
  },
  {
    "name": "Glitchpop",
    "gun": "Judge",
    "tier": "Select"
  },
  {
    "name": "Reaver",
    "gun": "Judge",
    "tier": "Exclusive"
  },
  {
    "name": "Sovereign",
    "gun": "Judge",
    "tier": "Deluxe"
  },
  {
    "name": "RGX 11z Pro",
    "gun": "Judge",
    "tier": "Select"
  },
  {
    "name": "RGX 2.0",
    "gun": "Judge",
    "tier": "Select"
  },
  {
    "name": "Horizon",
    "gun": "Judge",
    "tier": "Standard"
  },
  {
    "name": "BlastX",
    "gun": "Judge",
    "tier": "Standard"
  },
  {
    "name": "Nitro",
    "gun": "Judge",
    "tier": "Standard"
  },
  {
    "name": "Magepunk",
    "gun": "Judge",
    "tier": "Standard"
  },
  {
    "name": "Luxe",
    "gun": "Judge",
    "tier": "Select"
  },

  // Bucky
  {
    "name": "Reaver",
    "gun": "Bucky",
    "tier": "Exclusive"
  },
  {
    "name": "Sovereign",
    "gun": "Bucky",
    "tier": "Deluxe"
  },
  {
    "name": "RGX 11z Pro",
    "gun": "Bucky",
    "tier": "Select"
  },
  {
    "name": "RGX 2.0",
    "gun": "Bucky",
    "tier": "Select"
  },
  {
    "name": "BlastX",
    "gun": "Bucky",
    "tier": "Standard"
  },
  {
    "name": "Nitro",
    "gun": "Bucky",
    "tier": "Standard"
  },
  {
    "name": "Magepunk",
    "gun": "Bucky",
    "tier": "Standard"
  },
  {
    "name": "Champions 2023",
    "gun": "Bucky",
    "tier": "Standard"
  },
  {
    "name": "Luxe",
    "gun": "Bucky",
    "tier": "Select"
  },

  //bulldog
  {
    "name": "Elderflame",
    "gun": "Bulldog",
    "tier": "Deluxe"
  },
  {
    "name": "Glitchpop",
    "gun": "Bulldog",
    "tier": "Select"
  },
  {
    "name": "Reaver",
    "gun": "Bulldog",
    "tier": "Exclusive"
  },
  {
    "name": "Sovereign",
    "gun": "Bulldog",
    "tier": "Deluxe"
  },
  {
    "name": "RGX 11z Pro",
    "gun": "Bulldog",
    "tier": "Select"
  },
  {
    "name": "RGX 2.0",
    "gun": "Bulldog",
    "tier": "Select"
  },
  {
    "name": "Horizon",
    "gun": "Bulldog",
    "tier": "Standard"
  },
  {
    "name": "BlastX",
    "gun": "Bulldog",
    "tier": "Standard"
  },
  {
    "name": "Nitro",
    "gun": "Bulldog",
    "tier": "Standard"
  },
  {
    "name": "Magepunk",
    "gun": "Bulldog",
    "tier": "Standard"
  },
  {
    "name": "Luxe",
    "gun": "Bulldog",
    "tier": "Select"
  },

//guardian
{
  "name": "Horizon",
  "gun": "Guardian",
  "tier": "Standard"
},
{
  "name": "BlastX",
  "gun": "Guardian",
  "tier": "Standard"
},
{
  "name": "Nitro",
  "gun": "Guardian",
  "tier": "Standard"
},
{
  "name": "Magepunk",
  "gun": "Guardian",
  "tier": "Standard"
},
{
  "name": "Luxe",
  "gun": "Guardian",
  "tier": "Select"
},
{
  "name": "Glitchpop",
  "gun": "Guardian",
  "tier": "Select"
},
{
  "name": "Duality",
  "gun": "Guardian",
  "tier": "Deluxe"
},
{
  "name": "Elderflame",
  "gun": "Guardian",
  "tier": "Deluxe"
},
{
  "name": "Reaver",
  "gun": "Guardian",
  "tier": "Exclusive"
},
{
  "name": "Sovereign",
  "gun": "Guardian",
  "tier": "Deluxe"
},
{
  "name": "RGX 11z Pro",
  "gun": "Guardian",
  "tier": "Select"
},
{
  "name": "RGX 2.0",
  "gun": "Guardian",
  "tier": "Select"
},
{
  "name": "Champions 2023",
  "gun": "Guardian",
  "tier": "Standard"
},
{
  "name": "Sakura",
  "gun": "Guardian",
  "tier": "Standard"
},
{
  "name": "Prelude to Chaos",
  "gun": "Guardian",
  "tier": "Standard"
},




    // Vandal
    {
        "name": "Elderflame",
        "gun": "Vandal",
        "tier": "Deluxe"
      },
      {
        "name": "Glitchpop",
        "gun": "Vandal",
        "tier": "Select"
      },
      {
        "name": "Reaver",
        "gun": "Vandal",
        "tier": "Exclusive"
      },
      {
        "name": "Sovereign",
        "gun": "Vandal",
        "tier": "Deluxe"
      },
      {
        "name": "RGX 11z Pro",
        "gun": "Vandal",
        "tier": "Select"
      },
      {
        "name": "RGX 2.0",
        "gun": "Vandal",
        "tier": "Select"
      },
      {
        "name": "Horizon",
        "gun": "Vandal",
        "tier": "Standard"
      },
      {
        "name": "BlastX",
        "gun": "Vandal",
        "tier": "Standard"
      },
      {
        "name": "Nitro",
        "gun": "Vandal",
        "tier": "Standard"
      },
      {
        "name": "Magepunk",
        "gun": "Vandal",
        "tier": "Standard"
      },
      {
        "name": "Luxe",
        "gun": "Vandal",
        "tier": "Select"
      },
    
      // Phantom
      {
        "name": "Elderflame",
        "gun": "Phantom",
        "tier": "Deluxe"
      },
      {
        "name": "Glitchpop",
        "gun": "Phantom",
        "tier": "Select"
      },
      {
        "name": "Reaver",
        "gun": "Phantom",
        "tier": "Exclusive"
      },
      {
        "name": "Sovereign",
        "gun": "Phantom",
        "tier": "Deluxe"
      },
      {
        "name": "RGX 11z Pro",
        "gun": "Phantom",
        "tier": "Select"
      },
      {
        "name": "RGX 2.0",
        "gun": "Phantom",
        "tier": "Select"
      },
      {
        "name": "Horizon",
        "gun": "Phantom",
        "tier": "Standard"
      },
      {
        "name": "BlastX",
        "gun": "Phantom",
        "tier": "Standard"
      },
      {
        "name": "Nitro",
        "gun": "Phantom",
        "tier": "Standard"
      },
      {
        "name": "Magepunk",
        "gun": "Phantom",
        "tier": "Standard"
      },
      {
        "name": "Luxe",
        "gun": "Phantom",
        "tier": "Select"
      },





      //rifles
//marshal
{
  "name": "Prime",
  "gun": "Marshal",
  "tier": "Deluxe"
},
{
  "name": "Reaver",
  "gun": "Marshal",
  "tier": "Exclusive"
},
{
  "name": "Glitchpop",
  "gun": "Marshal",
  "tier": "Select"
},
{
  "name": "Sovereign",
  "gun": "Marshal",
  "tier": "Deluxe"
},
{
  "name": "RGX 11z Pro",
  "gun": "Marshal",
  "tier": "Select"
},
{
  "name": "RGX 2.0",
  "gun": "Marshal",
  "tier": "Select"
},
{
  "name": "Horizon",
  "gun": "Marshal",
  "tier": "Standard"
},
{
  "name": "BlastX",
  "gun": "Marshal",
  "tier": "Standard"
},
{
  "name": "Nitro",
  "gun": "Marshal",
  "tier": "Standard"
},
{
  "name": "Magepunk",
  "gun": "Marshal",
  "tier": "Standard"
},
{
  "name": "Luxe",
  "gun": "Marshal",
  "tier": "Select"
},

      //operator
    
        // Operator
        {
          "name": "Protocol",
          "gun": "Operator",
          "tier": "Standard"
        },
        {
          "name": "BlastX",
          "gun": "Operator",
          "tier": "Standard"
        },
        {
          "name": "Champions 2023",
          "gun": "Operator",
          "tier": "Standard"
        },
        {
          "name": "Sakura",
          "gun": "Operator",
          "tier": "Standard"
        },
        {
          "name": "Prelude to Chaos",
          "gun": "Operator",
          "tier": "Standard"
        },
        {
          "name": "Sovereign",
          "gun": "Operator",
          "tier": "Deluxe"
        },
        {
          "name": "RGX 11z Pro",
          "gun": "Operator",
          "tier": "Select"
        },
        {
          "name": "Oni",
          "gun": "Operator",
          "tier": "Deluxe"
        },
        {
          "name": "Reaver",
          "gun": "Operator",
          "tier": "Exclusive"
        },
        {
          "name": "Elderflame",
          "gun": "Operator",
          "tier": "Deluxe"
        },
        {
          "name": "Luxe",
          "gun": "Operator",
          "tier": "Select"
        },
        {
          "name": "Glitchpop",
          "gun": "Operator",
          "tier": "Select",
        },
        {
          "name": "Duality",
          "gun": "Operator",
          "tier": "Deluxe",
        },
        {
          "name": "Horizon",
          "gun": "Operator",
          "tier": "Standard",
        },
        {
          "name": "Magepunk",
          "gun": "Operator",
          "tier": "Standard",
        },
        {
          "name": "RGX 2.0",
          "gun": "Operator",
          "tier": "Select",
        },
        {
          "name": "Nitro",
          "gun": "Operator",
          "tier": "Standard",
        },
        {
          "name": "Radiant Guardian",
          "gun": "Operator",
          "tier": "Battle Pass",
        },

        //machine guns
        {
          "name": "Prime",
          "gun": "Ares",
          "tier": "Deluxe"
        },
        {
          "name": "Reaver",
          "gun": "Ares",
          "tier": "Exclusive"
        },
        {
          "name": "Sovereign",
          "gun": "Ares",
          "tier": "Deluxe"
        },
        {
          "name": "RGX 11z Pro",
          "gun": "Ares",
          "tier": "Select"
        },
        {
          "name": "RGX 2.0",
          "gun": "Ares",
          "tier": "Select"
        },
        {
          "name": "Horizon",
          "gun": "Ares",
          "tier": "Standard"
        },
        {
          "name": "BlastX",
          "gun": "Ares",
          "tier": "Standard"
        },
        {
          "name": "Nitro",
          "gun": "Ares",
          "tier": "Standard"
        },
        {
          "name": "Magepunk",
          "gun": "Ares",
          "tier": "Standard"
        },
        {
          "name": "Luxe",
          "gun": "Ares",
          "tier": "Select"
        },
//odin
{
  "name": "Prime",
  "gun": "Odin",
  "tier": "Deluxe"
},
{
  "name": "Glitchpop",
  "gun": "Odin",
  "tier": "Select"
},
{
  "name": "Reaver",
  "gun": "Odin",
  "tier": "Exclusive"
},
{
  "name": "Sovereign",
  "gun": "Odin",
  "tier": "Deluxe"
},
{
  "name": "RGX 11z Pro",
  "gun": "Odin",
  "tier": "Select"
},
{
  "name": "RGX 2.0",
  "gun": "Odin",
  "tier": "Select"
},
{
  "name": "Horizon",
  "gun": "Odin",
  "tier": "Standard"
},
{
  "name": "BlastX",
  "gun": "Odin",
  "tier": "Standard"
},
{
  "name": "Nitro",
  "gun": "Odin",
  "tier": "Standard"
},
{
  "name": "Magepunk",
  "gun": "Odin",
  "tier": "Standard"
},
{
  "name": "Luxe",
  "gun": "Odin",
  "tier": "Select"
},

      ];
      

</script>

<template>
  <main>
   

  </main>
</template>
