<template>
  <header id="nav_website">
    <nav class="navbar navbar-expand-sm bg-light navbar-light">
      <div class="container-fluid">
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav nav_ul pt-2 mx-auto">
            <li class="nav-item">
              <a href="#presentation" class="nav-link nav_a text-black">Présentation</a>
            </li>
            <li class="nav-item">
              <a href="#services" class="nav-link nav_a text-black">Services</a>
            </li>
            <li class="nav-item">
              <a href="#competences" class="nav-link nav_a text-black">Compétences</a>
            </li>
            <li class="nav-item">
              <a href="#portfolio" class="nav-link nav_a text-black">Portfolio</a>
            </li>
            <li class="nav-item">
              <a href="#contact" class="nav-link nav_a text-black">Contact</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>

export default {
    name: 'NavWebsite'
}

</script>

<style scoped>

.nav_a
{
  text-align: left;
  padding: 3px 0px;
  font: 700 1.2em 'Times', sans-serif;
  transition: 0.8s linear;
  letter-spacing: 1px;
  background-size: 100%;
}
.nav_a:hover
{
  --fill-color: #a6ddf7;
  background: linear-gradient(var(--fill-color) 0 100%) right / 0 no-repeat; 
}

@media all and (min-width: 370px) and (max-width: 767px)
{
  .nav_a{
    text-transform: none;
  }
}

</style>