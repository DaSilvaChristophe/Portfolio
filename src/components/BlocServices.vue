<template>
  <section id="services" class="transition_page bg-light d-flex flex-column pb-4">
    <h2 class="pt-2">Services</h2>
    <div class="container-fluid">
        <div class="row d-flex justify-content-around flex-wrap">
            <div v-for="item of items" class="bg-light col-10 col-sm-5 col-lg-3 my-3 mr-2 me-2" style="height: 21rem">
                <div class="d-flex flex-column justify-content-center align-items-center rounded bg-light" style="height: 20rem">
                    <p class="card-text title rounded-pill">{{ item.title }}</p>
                    <img v-bind:src="item.icon" alt="" class="mx-auto rounded-pill" style="height: 10rem">
                    <p class="pt-3"> {{ item.description }} </p>
                </div>
            </div>
        </div>
    </div>
  </section>
</template>

<script>

import imgProjectWeb from "../assets/projet_web.jpg";
import imgDeveloppement from "../assets/developpement.jpg";
import imgAccompagnement from "../assets/accompagnement.jpg";
import imgSeo from "../assets/seo.jpg";
import imgMaintenance from "../assets/maintenance.jpg";


export default {
  name: 'BlocServices',
  data(){
      return {
          items: [
              { title: 'Developpement Web',
                icon: imgDeveloppement,
                description:'Travaux sur langages de programmations, Base de données, CMS.. Frontend and Backend.'
              },
              { title: 'Projet Web',
                icon: imgProjectWeb,
                description:'Site vitrine professionnel, E-Commerce, Applications de bureau, Intégration API, Blog..'
              },
              { title: 'Accompagnement',
                icon: imgAccompagnement,
                description:'Accompagnement dans le processus de création puis a la mise en production sur demande'
              },
              { title: 'Référencement',
                icon: imgSeo,
                description:'Bases du SEO pour votre référencement web. Audit, Optimisation, SEO local sur demande.'
              },
              { title: 'Maintenance de site',
                icon: imgMaintenance,
                description:'Maintenance de site après création sur demande. Reprise sur site web déjà en production'
              },      
          ],
      }
  },
}

</script>

<style scoped>

.back
{
     background: linear-gradient(220.64deg, #C8F5FF 0%, #B4B4FF 100%);
}

h2
{
  font-size: 3em;
  color: black;
}

img
{
    box-sizing: border-box;
    object-fit: cover;
    width: 100%;
    height: 75%;
}

.title
{
  width: 90%;
  font-size: 1.1em;
  color: black;
  font-weight: bold;
  max-width: 800px;
  padding: 0 0px;
  background: white;
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

/* Media Queries */

@media all and (min-width: 585px) and (max-width: 768px)
{
  h2
  {
    font-size: 3em;
  }
}

@media all and (min-width: 500px) and (max-width: 584px)
{
  h2
  {
    font-size: 2.6em;
  }
}

@media all and (min-width: 320px) and (max-width: 499px)
{
  h2
  {
    font-size: 2.3em;
  }
}

</style>