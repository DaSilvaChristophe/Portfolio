<template>
  <section class="showcase">
    <header>
      <div @click="nav()" class="toggle"></div>
    </header>
    <div class="overlay"></div>
    <div class="text mb-3">
      <div>
        <video loop src="" muted="" autoplay=""></video>
        <h1><span>Cr</span>eati<span>vi</span>ty Vis<span>ion</span></h1>
      </div>
      <div id="anim">
        <h2 id="target" class="mt-3">Developpement Web <br> `</h2>
      </div>
      <ButtonExpansive @click="website()" v-html="message"/>
    </div>
  </section>
  <div class="menu">
    <ul>
      <li><a href="/website#presentation">Présentation</a></li>
      <li><a href="/website#services">Services</a></li>
      <li><a href="/website#competences">Compétences</a></li>
      <li><a href="/website#portfolio">Portfolio</a></li>
      <li><a href="/website#contact">Contact</a></li>
    </ul>
  </div>
</template>

<script>
import Copywriting from '@/components/others/Copywriting.vue';
import ButtonExpansive from '@/components/buttons/ButtonExpansive.vue';

export default {
  name: 'home',
  components: { Copywriting, ButtonExpansive
  },
  mounted() {

    /* Animation letters */
    const target = document.getElementById("target");

    let array = ["Frontend`", "Backend`", "SEO`","CMS`"];
    let wordIndex = 0;
    let letterIndex = 0;

    const createLetter = () => {
        const letter = document.createElement("span");
        target.appendChild(letter);

        letter.textContent = array[wordIndex][letterIndex];

        setTimeout(() => {
            letter.remove();
        }, 2800)
    }
    
    // Fonction récursif
    const loop = () => {
        setTimeout(() => {
            if (wordIndex >= array.length) {
                wordIndex = 0;
                letterIndex = 0;
                loop();
            } else if (letterIndex < array[wordIndex].length) {
                createLetter();
                letterIndex++;
                loop();
            } else {
                wordIndex++
                letterIndex = 0;
                setTimeout(() => {
                    loop();
                }, 2800); 
            }
        }, 60)
    }

    loop();
  },
  data(){
    return {
      message: 'Website'
    }
  },
  methods: {
    nav(){
      const menuToggle = document.querySelector('.toggle');
      const showcase = document.querySelector('.showcase');
      menuToggle.classList.toggle('active');
      showcase.classList.toggle('active');
    },
    website(){
      location.href = "/website"
    }
  },
}
</script>

<style scoped>

*
{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

header
{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  padding: 40px 100px;
  z-index: 1000;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

.toggle
{
  position: relative;
  bottom: 30px;
  left: 30px;
  width: 60px;
  height: 60px;
  background: url(https://i.ibb.co/HrfVRcx/menu.png);
  background-repeat: no-repeat;
  background-size: 30px;
  background-position: center;
  cursor: pointer;
}
.toggle.active
{
  background: url(https://i.ibb.co/rt3HybH/close.png);
  background-repeat: no-repeat;
  background-size: 25px;
  background-position: center;
  cursor: pointer;
}

.showcase
{
  position: absolute;
  right: 0;
  width: 100%;
  min-height: 99vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #111;
  transition: 0.5s;
  z-index: 2;
}
.showcase.active
{
  right: 200px;
}

.overlay
{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #03a9f4;
  mix-blend-mode: overlay;
}

video{
  position: absolute;
  top: 5px;
  left:0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  pointer-events: none;
  z-index: 1;
  mix-blend-mode: screen;
  margin-bottom: 50px;
}

.text
{
  z-index: 3;
}
.text h1
{
  position: relative;
  font-size: 4.5em;
  font-weight: 800;
  color: #fff;
  line-height: 1.5em;
  text-transform: uppercase;
  z-index: 1;
  border-bottom: 2px solid white;
}
h1 span {
   color: #42bdf7;
}
.text h2
{
  font-size: 3.5em;
  font-weight: 600;
  color: black;
  line-height: 1.3em;
  text-transform: uppercase;
  background: linear-gradient(0deg, rgba(254,254,226,1) 10%, rgba(188,221,222,1) 100%);
  padding: 8px;
  border-radius: 20px;
}

.menu
{
  position: absolute;
  top: 0;
  right: 0;
  width: 200px;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  font-weight: 700;
  font-style: italic;
  background: linear-gradient(0deg, rgba(254,254,226,1) 10%, rgba(188,221,222,1) 100%);
}
.menu ul
{
  position: relative;
}
.menu ul li
{
  list-style: none;
}
.menu ul li a
{
  text-decoration: none;
  font-size: 24px;
  color: #111;
}
.menu ul li a:hover
{
  color: #42bdf7;
}

/* Média Queries */

@media all and (min-width: 651px) and (max-width: 991px)
{
  .showcase,
  .showcase header
  {
    padding: 40px;
  }
  .text h2
  {
    font-size: 3em;
  }
}

@media all and (min-width: 559px) and (max-width: 650px)
{
  .showcase,
  .showcase header
  {
    padding: 40px;
  }
  .text h1
  {
    font-size: 4em;
  }
  .text h2
  {
    font-size: 2.5em;
  }
}

@media all and (min-width: 471px) and (max-width: 558px)
{
  .showcase,
  .showcase header
  {
    padding: 40px;
  }
  .text h1
  {
    font-size: 3.5em;
  }
  .text h2
  {
    font-size: 2em;
  }
}

@media all and (min-width: 370px) and (max-width: 470px)
{
  .showcase,
  .showcase header
  {
    padding: 40px;
  }
  .text h1
  {
    font-size: 3em;
  }
  .text h2
  {
    font-size: 1.5em;
  }
}


/* Animation Letters */

#target::after {
  content: '';
  transform: translateY(-4px);
  right: -5px;
  animation: anim 0.8s linear infinite;
}

@keyframes anim {
  50% {
    opacity: 0.1;
  }
  100% {
    opacity: 1;
  }
}
</style>



