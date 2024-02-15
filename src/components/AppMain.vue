<script>
export default {
  name: 'MainApp',
  props: ['projects'],
};
</script>
<template>
  <div class="container">
    <div class="row mt-3 g-3">
      <div class="col col-md-4" v-for="project in projects">
        <div class="card">
          <h5 class="card-header bg-primary">{{ project.title }}</h5>
          <div class="card-body">
            <h5 class="card-title">Creato: {{ project.created_date }}</h5>
            <p class="card-text">{{ project.description }}</p>
            <a href="#" class="btn btn-warning">Go somewhere</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style></style>
