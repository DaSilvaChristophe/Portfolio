<template>
  <div class="website">
    <NavWebsite/>
    <Presentation/>
    <BlocServices/>
    <Competences/>
    <Portfolio/>
    <Contact/>
  </div>
</template>

<script>
import NavWebsite from '@/components/nav/NavWebsite.vue'
import Presentation from '@/components/Presentation.vue'
import BlocServices from '@/components/BlocServices.vue'
import Competences from '@/components/Competences.vue'
import Portfolio from '@/components/Portfolio.vue'
import Contact from '@/components/Contact.vue'


export default {
  name: 'website',
  components: {
    NavWebsite, Presentation,BlocServices, Competences, Portfolio, Contact
  }
}
</script>