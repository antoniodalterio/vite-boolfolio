<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
  name: 'BoolFolio',
  data() {
    return {
      projects: [],
    };
  },

  components: {
    AppHeader,
    AppMain,
  },
  methods: {
    getProject() {
      axios
        .get('http://127.0.0.1:8000/api/test')
        .then((response) => {
          console.log(response);
          this.projects = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  created() {
    this.getProject();
  },
};
</script>

<template>
  <AppHeader></AppHeader>
  <AppMain :projects="projects"></AppMain>
  <router-view></router-view>
</template>

<style scoped></style>
