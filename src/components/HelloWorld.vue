<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>
   <div id="cardContainer"> 
  <div class="card">
    <div>
      <h1 class="heading">
        HAX THE WEB
      </h1>
    </div>
    <img src="https://hax.psu.edu/assets/HAXLogo.svg">
    <p>
      Hax logo taken directly from hax.psu.edu
    </p>
    <a href = "https://hax.psu.edu"><button class="details">
      Details
      </button></a>
  </div>
  <div class="card">
    <div>
      <h1 class="heading">
        HAX THE WEB
      </h1>
    </div>
    <img src="https://hax.psu.edu/assets/HAXLogo.svg">
    <p>
      Hax logo taken directly from hax.psu.edu
    </p>
    <a href = "https://hax.psu.edu"><button class="details">
      Details
      </button></a>
  </div>
  <div class="card">
    <div>
      <h1 class="heading">
        HAX THE WEB
      </h1>
    </div>
    <img src="https://hax.psu.edu/assets/HAXLogo.svg">
    <p class="detailP">
      Hax logo taken directly from hax.psu.edu
    </p>
    <!--<a href = "https://hax.psu.edu">--><button class="details">
      Details
      </button><!--</a>-->
  </div>
</div>
<button class="cardDuplicator">
  Make a new card
</button>
<button class="changeHeading">
  Heading changer
</button>
<button class="cardColorChanger">
  Change backround color
</button>
<button class="cardDeleter">
  Delete last card
</button>
<script> 
  document.querySelector('.cardDuplicator').addEventListener('click', (e) => {
  const card = document.querySelector(".card");
  console.log(document.getElementById("cardContainer"));
  document.getElementById("cardContainer").appendChild(card);
})
  document.querySelector('.changeHeading').addEventListener('click', (e) => {
    document.querySelector(".heading").innerHTML="something else"
  })
  document.querySelector('.cardDeleter').addEventListener('click', (e) => {
    document.querySelector("#cardContainer").remove(document.querySelector("#cardContainer").lastChild);
  })
  document.querySelector('.cardColorChanger').addEventListener('click', (e) => {
    document.querySelector('.card').style.backgroundColor='red';
  })
  document.querySelector('.details').addEventListener('click', (e) => {
    if(document.querySelector('.detailP').style.visibility==visible)
    {document.querySelector('.detailP').style.visibility="hidden"}
    else{document.querySelector('.detailP').style.visibility="visible"}
  })
</script>
  <!-- not sure why the above script refuses to work. For some reason it refuses to add the cards in spite of all of my elements being referenced correctly, i was printong them to console. It does not like append child, and says it is being called from null whereas i can clearly print what it is called on so at the very least it is not null-->

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
