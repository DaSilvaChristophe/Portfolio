<template>
  <section id="presentation" class="showcase transition_page">
    <div class="container-fluid flex">
      <div class="anim_reflection">
        <div class="mt-4">
          <img src="../assets/presentation.png" class="rounded" alt="">
        </div>
      </div>
       <h1 class="py-2">Creativity Vision</h1>
      <div class="text">
        <h2 class="pt-4 pb-2 mx-auto">'About Me'</h2>
        <p class="py-2 rounded mx-auto">
          Développeur web au service d'entreprises, entrepreneurs et particuliers qui souhaite créer leur site, développer de nouveaux concepts via la création d'applications ou simplement intégrer de nouvelles fonctionnalités sur site existant, je suis a l'écoute de vos projets pour leur réalisation.
          <br><br>
          Développement de business (site vitrine professionnel, e-commerce, applications de bureau) ou personnel (blog).
          <br><br>
          Travaux sur langages de programmations, Base de données, CMS..
          <br>
          Audit et Optimisation SEO (Référencement web)..
          <br>
          Maintenance de site web..
        </p>
        <ButtonExpansive @click="contact()" v-html="message_button"/>
      </div>
    </div>
  </section>
</template>

<script>

import NavWebsite from '@/components/nav/NavWebsite.vue'
import ButtonExpansive from '@/components/buttons/ButtonExpansive.vue'

export default {
  name: 'Presentation',
  components: {
    NavWebsite , ButtonExpansive
  },
  data(){
    return {
      message_button: 'Contact'
    }
  },
  methods: {
    contact(){
      location.href = "#contact"
    }
  }
}

</script>

<style scoped>

.showcase
{
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background: white;
}

h1
{
  font-size: 3.7em;
  font-weight: 500;
  color: black;
  line-height: 1.5em;
}

img
{
  width: 85%;
}


.text h2
{
  width: 70%;
  font-size: 1.8em;
  font-weight: 500;
  color: rgb(25, 29, 25);
  line-height: 1em;
  border-top: 1px solid black;
}
.text p
{
  width: 100%;
  font-size: 1.1em;
  color: black;
  font-weight: 400;
  max-width: 800px;
  padding: 0 30px;
  background: white;
}
a
{
  display: inline-block;
  font-size: 0.8em;
  background: #fff;
  padding: 8px 30px;
  margin-bottom: 30px;
  text-transform: uppercase;
  text-decoration: none;
  margin-top: 10px;
  color: black;
  letter-spacing: 2px;
  transition: 0.2s;
  cursor: pointer;
  border: 1px solid black;
}
a:hover
{
  background: black;
  color: white;
  letter-spacing: 4px;
  cursor: pointer;
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

/* Animation reflection img */

.anim_reflection div {
	position: relative;
}
.anim_reflection div::before {
	position: absolute;
	top: 0;
	left: -75%;
	z-index: 2;
	display: block;
	content: '';
	width: 50%;
	height: 100%;
	background: -webkit-linear-gradient(left, rgba(255,255,255,0) 0%, rgba(255,255,255,.3) 100%);
	background: linear-gradient(to right, rgba(255,255,255,0) 0%, rgba(255,255,255,.3) 100%);
	-webkit-transform: skewX(-25deg);
	transform: skewX(-25deg);
}

.anim_reflection div:hover::before {
	-webkit-animation: reflection 3s forwards;
	animation: reflection 3s forwards;
}

@-webkit-keyframes reflection {
	100% {
		left: 43%;
	}
}
@keyframes reflection {
	100% {
		left: 43%;
	}
}

/* Media Queries */

@media all and (min-width: 769px) and (max-width: 991px)
{
  .showcase
  {
    padding: 0 10px;
    padding-right: 20px;
  }
  img
  {
    width: 100%;
    margin: auto;
  }
}

@media all and (min-width: 585px) and (max-width: 768px)
{
  .showcase
  {
    padding: 0 10px;
    padding-right: 20px;
  }
  img
  {
    width: 100%;
    margin: auto;
  }
  h1
  {
    font-size: 3em;
  }
  .text h2
  {
    font-size: 1.6em;
  }
}

@media all and (min-width: 500px) and (max-width: 584px)
{
  .showcase
  {
    padding: 0 10px;
    padding-right: 20px;
  }
  img
  {
    width: 100%;
    margin: auto;
  }
  h1
  {
    font-size: 2.6em;
  }
  .text h2
  {
    font-size: 1.4em;
  }
  .text P{
    font-size: 0.9em;
  }
  a{
    font-size: 0.7em;
  }
}

@media all and (min-width: 320px) and (max-width: 499px)
{
  .showcase
  {
    padding: 0 10px;
    padding-right: 20px;
  }
  img
  {
    width: 100%;
    margin: auto;
  }
  h1
  {
    font-size: 1.9em;
  }
  .text h2
  {
    font-size: 1.4em;
  }
  .text P{
    font-size: 0.9em;
  }
  a{
    font-size: 0.7em;
  }
}

</style>
