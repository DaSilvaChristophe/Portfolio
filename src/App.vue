<template>
  <div>
    <router-link to="/"></router-link>
    <router-link to="/website"></router-link>
  <router-view/>
  </div>
</template>

<script>

export default {
  name: 'App',
}
</script>
<style lang="scss">
#app 
{
  text-align: center;
 
}

*
{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Times', sans-serif;
    .modal-backdrop.fade.show
    {
      display: none;
    }
}
</style>
