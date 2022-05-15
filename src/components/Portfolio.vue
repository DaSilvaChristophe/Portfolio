<template>
  <section id="portfolio" class="transition_page bg-light d-flex flex-column pb-4">
    <h2 class="pt-2">Portfolio</h2>
    <div class="container-fluid">
        <div class="row d-flex justify-content-around align-items-center flex-wrap">
            <div v-for="item of items" class="bloc-website-ext bg-light col-5 col-sm-10 col-md-5 mb-3 d-flex justify-content-around align-items-center flex-wrap rounded" style="height: 21rem">
              <div class="test col-10 d-flex flex-column justify-content-center align-items-center rounded bg-light" style="height: 20rem">
                <p class="title rounded-pill">{{ item.title }}</p>
                <img v-bind:src="item.img" alt="" class="mx-auto border rounded shadow" style="height: 13rem">
                <ButtonExpansive @click="website_ext()" v-html="button"/>
              </div>
            </div>
            <div v-for="site of description" class="bloc-description col-5 col-sm-9 col-md-5 rounded shadow">
              <div class="top-line">{{site.title}}</div>
              <div class="headline pt-4">{{site.description}}</div>
              <div class="poste">{{site.poste}}</div>
            </div>
        </div>
    </div>
    <div class="pt-4">
      <h3>"Others Project Soon in the Website"</h3>
    </div>
  </section>
</template>

<script>

import ButtonExpansive from "@/components/buttons/ButtonExpansive.vue";
import imgCIL from "../assets/coeurinlove.png";

export default {

  name: 'Portfolio',
  components: {
    ButtonExpansive
  },
  data(){
      return {
          button: 'Voir Site',
          items: [
              { title: 'ArtsCoeurInLoveAgency',
                img: imgCIL,
              },    
          ],
          description: [
              { title: 'Création - Maintenance CMS',
                description:'Réalisation de site web sous CMS (Wix) pour une agence artistique basé sur Fontainebleau/Avon. Création du Google my business et analytics entreprise, optimisation SEO du site, gestion de suivi : amélioration et intègration de nouveauté a la demande client. Design réalisé en collaboration avec le client.',
                poste: 'En collaboration depuis fév. 2020'
              },    
          ],
      }
  },
  methods: {
    website_ext(){
      window.open('https://www.coeurinlove.com/', '_blank')
    }
  }
}

</script>

<style scoped>

h2
{
  font-size: 3em;
  color: black;
}

.title
{
  width: 90%;
  font-size: 1.5em;
  color: black;
  font-weight: bold;
}
img
{
  box-sizing: border-box;
  object-fit: cover;
  width: 100%;
  height: 100%;
}
a
{
  font-size: 0.9em
}
a:hover
{
background: black;
color: white;
}

.bloc-description
{
    height: 90%;
    display: flex;
    flex-direction: column;
    align-items: center;    
    font-family: 'Times', sans-serif;
    border-radius: 2px;
    padding: 5px 5px;
    background: linear-gradient(220.64deg, #C8F5FF 0%, #B4B4FF 100%)
}
.top-line 
{
    font-size: 24px;
    font-weight: bold;
}
.headline 
{
    width: 90%;
    font-size: 15px;
}
.poste 
{
    font-size: 20px;
    font-weight: bold;
    padding-top: 25px;
}

h3
{
  font-size: 2.2em;
  color: black;
}
/* Animation transition page */

.transition_page {
  animation: opacity 3s linear forwards;
}

@keyframes opacity {
0% {
    opacity: 0;
  }
  50% {
    opacity: 0.7;
  }
  100% {
    opacity: 1;
  }
}

.clignote 
{
  animation: clignote 3s infinite;
}

@keyframes clignote {
  0% {
    opacity: 1;
    color: #0065fc;
  }
  25% {
    opacity: 0.5;
    color: #0065fc;
  }
  50% {
    opacity: 1;
    color: #0065fc;
  }
  75% {
    opacity: 0.5;
    color: #0065fc;
  }
  100% {
    opacity: 1;
    color: #0065fc;
  }
}

/* Media Queries */

@media all and (min-width: 768px) and (max-width: 999px)
{
  .title
  {
    font-size: 21px;
  }
}

@media all and (min-width: 585px) and (max-width: 767px)
{
  .title
  {
    font-size: 21px;
  }
}

@media all and (min-width: 500px) and (max-width: 584px)
{
  h2
  {
    font-size: 2.6em;
  }
  .bloc-website-ext
  {
    width: 90%;
  }
  .title
  {
    font-size: 21px;
  }
  .bloc-description
  {
    width: 80%;
  }
  .top-line 
  {
      font-size: 22px;
  }
  .headline 
  {
      font-size: 14px;
  }
  .poste 
  {
      font-size: 18px;
  }
  h3
  {
    font-size: 2em;
  }
}

@media all and (min-width: 320px) and (max-width: 499px)
{
  h2
  {
    font-size: 2.3em;
  }
   .bloc-website-ext
  {
    width: 90%;
  }
  .title
  {
    font-size: 21px;
  }
  .bloc-description
  {
    width: 80%;
  }
  .top-line 
  {
      font-size: 20px;
  }
  .headline 
  {
      font-size: 14px;
  }
  .poste 
  {
      font-size: 18px;
  }
  h3
  {
    font-size: 1.4em;
  }
}

</style>