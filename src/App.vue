<script setup>
import WeatherWidget from './components/WeatherWidget.vue'
</script>

<template>
  <div class="container">
    <div class="grid">
      <div class="main-content">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Sint, repellat
        assumenda ab ipsa ducimus recusandae in dolorum obcaecati maxime
        cupiditate provident sequi neque ipsum laboriosam earum. Itaque
        asperiores facilis inventore delectus. Beatae explicabo repellat
        voluptatem culpa, sequi laborum vitae consequatur ea id cumque commodi
        atque est fugiat quae? Rerum ad doloribus error perferendis architecto
        neque dolor incidunt suscipit facere maiores dolore labore, officiis
        rem. Enim ullam, qui eaque placeat in labore, repellat, omnis
        exercitationem impedit vitae eveniet et vero nostrum consectetur
        obcaecati odio. Laborum voluptatem architecto molestias, adipisci animi
        ea, placeat tenetur dolorum soluta, praesentium aut maiores nobis dolore
        totam.

        <WeatherWidget />
      </div>
      <div class="sidebar">
        sidebar. Lorem ipsum dolor sit amet consectetur adipisicing elit. Harum
        atque deserunt aliquid blanditiis magni odit dicta. Libero aliquam
        recusandae enim, in quas numquam esse possimus earum nihil amet
        voluptates voluptatum sit magnam, repellat eveniet laudantium excepturi.
        Labore explicabo a accusamus! Mollitia amet possimus error fugiat
        molestiae molestias ipsam. Doloremque perferendis aperiam molestiae iure
        qui autem possimus obcaecati ab odio deleniti amet, dignissimos vero rem
        voluptate. Possimus veniam voluptates aut. Quasi eius cumque ullam. Quos
        iusto aut sint blanditiis reiciendis autem quo numquam, repellat
        sapiente ex vitae, ea officiis quaerat deleniti a? Nemo accusamus a
        voluptate est veritatis qui magni quod.
      </div>
    </div>
  </div>
</template>

<style>
.container {
  max-width: 900px;
  margin: auto;
}

.grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 30px;
}

.sidebar,
.main-content {
  container-type: inline-size;
}

@media (min-width: 800px) {
  .grid {
    grid-template-columns: 2fr 1fr;
  }
}
</style>
