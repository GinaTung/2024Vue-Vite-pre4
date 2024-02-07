<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h3>{{ data }}</h3>

  </div>
</template>

<script>
export default {
  data(){
    return {
      data:{}
    }
  },
  mounted(){
    console.log(import.meta.env.VITE_PATH);
    console.log(import.meta.env.VITE_TEXT);
    const url = import.meta.env.VITE_PATH
    this.$http.get(url).then((response) => {
        // console.log(response)
        this.data = response.data.results[0];
        // console.log(this.data);
      })
  }
}
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
}
</style>
