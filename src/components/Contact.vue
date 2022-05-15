<template>
  <section id="contact" class="container-fluid bg-white transition_page d-flex flex-column pb-4">
    <div class="bloc-component row d-flex justify-content-center align-items-center w-100 pt-3">
      <div class="bloc-iframe col-md-6 col-sm-7">
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2650.132019943766!2d2.7889954150366156!3d48.377200142420875!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47ef5fe8f8d7ebb7%3A0x2ad5b4b2f36b8ed!2s113%20Av.%20de%20Fontainebleau%2C%2077250%20Moret-Loing-et-Orvanne!5e0!3m2!1sfr!2sfr!4v1652572048847!5m2!1sfr!2sfr" height="400" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade" class="text-center"></iframe>
      </div>
      <div class="bloc-contact col-md-6 col-sm-5">
        <h2 class="pb-2">Creativity Vision</h2>
        <address>Mr Da Silva Christophe <br> 113 Avenue de Fontainebleau <br> 77250 Veneux-les-sablons</address>
        <p>Téléphone : 07.69.40.29.57</p>
        <ButtonExpansive @click="contact()" v-html="button"/>
        <div class="mt-4 d-flex justify-content-center align-items-center">
          <Social/>
        </div>
      </div>
    </div>
    <div class="mt-3">
      <ModalMentionsLegales v-html="button"/>
      <Copywriting/>
    </div>
  </section>
</template>

<script>

import ModalMentionsLegales from '@/components/others/ModalMentionsLegales.vue'
import Copywriting from '@/components/others/Copywriting.vue'
import ButtonExpansive from '@/components/buttons/ButtonExpansive.vue'
import Social from '@/components/others/Social.vue'

export default {
  name: 'Contact',
  components: {
    Copywriting, ButtonExpansive, Social, ModalMentionsLegales
  },
  data(){
    return {
      button: 'Contact',
    }
  },
  methods: {
    contact(){
      location.href = "mailto:crisinvest88@gmail.com"
    }
  }
}

</script>

<style scoped>

iframe
{
  width: 90%;
}

h2
{
  font-size: 2.5em;
  color: black;
}

address, p
{
 font-size: 1.1em;
}

a
{
  border: 1px solid black;
  font-size: 0.9em
}

a:hover
{
  background: black;
  color: white;
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

@media all and (min-width: 607px) and (max-width: 768px)
{
  h2
  {
    font-size: 2em;
  }
  address, p
  {
    font-size: 1em;
  }
}

@media all and (min-width: 370px) and (max-width: 606px)
{
  .bloc-component
  {
    display: flex;
    flex-direction: column-reverse;
  }
  .pt-5 {
    padding-top: 0;
  }
  .bloc-iframe
  {
    width: 90%;
    padding-top: 20px;
  }
  iframe{
    height: 200px;
  }
  .bloc-contact
  {
    width: 100%;
    margin-top: 0;
  }
  h2
  {
    font-size: 2em;
  }
   address, p
  {
    font-size: 1em;
  }
}

</style>