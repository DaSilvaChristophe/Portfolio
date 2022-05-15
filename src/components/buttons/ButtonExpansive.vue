<template>
     <a class="mt-3 fw-bold rounded"></a>
</template>

<script>
export default {
    name: 'ButtonExpansive',
}
</script>

<style scoped>
a
{
  display: inline-block;
  font-size: 1em;
  background: #fff;
  padding: 8px 30px;
  text-transform: uppercase;
  text-decoration: none;
  margin-top: 10px;
  color: black;
  letter-spacing: 2px;
  transition: 0.2s;
  cursor: pointer;
}
a:hover
{
  background: #42bdf7;
  color: white;
  letter-spacing: 4px;
  cursor: pointer;
}
</style>