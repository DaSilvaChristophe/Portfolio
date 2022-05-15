<template>
  <section id="competences" class=" transition_page bg-white pb-2">
      <h2 class="pt-2">Compétences</h2>
      <div class="graph-size py-3 mx-auto">
        <canvas id="myChart"></canvas>
      </div>
      <h3>Others</h3>
      <div class="graph-size py-3 mx-auto">
        <canvas id="myChartTwo"></canvas>
      </div>
 </section>
</template>

<script>

export default {
  name: 'Competences',
  mounted() {
    // Graph One (Langages, Frameworks and DataBases)
    const ctx = document.getElementById('myChart').getContext('2d');
    const myChart = new Chart(ctx, {
      type: 'bar',
      data: {
        labels: ['HTML5', 'CSS3', 'Javascript', 'Vue.js', 'Node.js', 'Bootstrap','', 'MongoDB', 'MySQL'],
        datasets: [{
            label: 'Langages, Frameworks and DataBases',
            data: [85, 80, 80, 75, 70, 80, 100, 70, 65],
            backgroundColor: [
              'rgba(255, 87, 51, 0.8)',
              'rgba(35, 55, 236, 0.8)',
              'rgba(250, 239, 74, 0.8)',
              'rgba(95, 178, 59, 0.8)',
              'rgba(101, 212, 53, 0.8)',
              'rgba(125, 38, 239, 0.8)',
              'rgba(0, 0, 0, 0)',
              'rgba(71, 228, 59, 0.8)',
              'rgba(255, 87, 51, 0.8)'
            ],
            borderColor: [
              'rgba(255, 87, 51, 0.8)',
              'rgba(35, 55, 236, 0.8)',
              'rgba(250, 239, 74, 0.8)',
              'rgba(95, 178, 59, 0.8)',
              'rgba(101, 212, 53, 0.8)',
              'rgba(125, 38, 239, 0.8)',
              'rgba(0, 0, 0, 0)',
              'rgba(71, 228, 59, 0.8)',
              'rgba(255, 87, 51, 0.8)'
            ],
            borderWidth: 1
        }]
      },
      options: {
          scales: {
              y: {
                  beginAtZero: true
              }
          }
      }
  });
  // Graph One (Others)
  const ctxTwo = document.getElementById('myChartTwo').getContext('2d');
  const myChartTwo = new Chart(ctxTwo, {
    type: 'polarArea',
    data: {
      labels: ['API REST','Git','GitHub','SCSS','Méthodologie BEM','SEO','','Google Analytics/Business','CMS','Adobe Acrobat Pro','Accessibilité',],
      datasets: [{
            label: 'Others Compétences',
            data: [70, 65, 75, 80, 90, 80, 100, 85, 80, 75, 70,], 
            backgroundColor: [
              'rgba(116, 229, 238, 0.8)',
              'rgba(233, 60, 60, 0.8)',
              'rgba(255, 255, 255, 0.8)',
              'rgba(218, 88, 213, 0.8)',
              'rgba(44, 220, 62, 0.8)',
              'rgba(27, 125, 223, 0.8)',
              'rgba(255, 255, 255, 1)',
              'rgba(255, 213, 71, 0.8)',
              'rgba(57, 90 , 255, 0.8)',
              'rgba(255, 37, 37, 0.8)',
              'rgba(255, 196, 57, 0.8)',
            ],
            borderColor: [
              'rgba(116, 229, 238, 0.8)',
              'rgba(233, 60, 60, 0.8)',
              'rgba(0, 0, 0, 0.3)',
              'rgba(218, 88, 213, 0.8)',
              'rgba(44, 220, 62, 0.8)',
              'rgba(27, 125, 223, 0.8)',
              'rgba(255, 255, 255, 0.8)',
              'rgba(255, 213, 71, 0.8)',
              'rgba(57, 90 , 255, 0.8)',
              'rgba(255, 37, 37, 0.8)',
              'rgba(255, 196, 57, 0.8)',
            ],
            borderWidth: 1
        }]
      }, 
    });
  }
}

</script>

<style scoped>

.graph-size
{
  width: 60%;
}

h2
{
  font-size: 3em;
  color: black;
}
h3
{
  font-size: 2.5em;
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

/* Media Queries */

@media all and (min-width: 585px) and (max-width: 768px)
{
  h2
  {
    font-size: 3em;
  }
  .graph-size
  {
  width: 75%;
  }
}

@media all and (min-width: 500px) and (max-width: 584px)
{
  h2
  {
    font-size: 2.6em;
  }
  h3
  {
    font-size: 2.2em;
  }
  .graph-size
  {
  width: 80%;
  }
}

@media all and (min-width: 370px) and (max-width: 499px)
{
  h2
  {
    font-size: 2.3em;
  }
  h3
  {
    font-size: 1.8em;
  }
  .graph-size
  {
  width: 90%;
  }
}

</style>





