<template>
  <div class="home">
      <div class="container">
          <h4><span class="g">Exhange</span> Rate App</h4>
          <span>You can check and calculate exhange rate in this app.
           All stats we had taken in <a class="g" href="https://api.privatbank.ua/#p24/exchange" target="_blank">PrivatBank</a>.
            Enjoy life and have a nice day! <i class="far fa-smile-wink"></i></span>
      </div>
  </div>
</template>
<style scoped="">
    span{
        white-space: pre-line;
        text-align: justify;
        padding-top: 10px;
        display: block;
    }
    .g{
        color: #42b983;
        display: inline-block;
        padding: 0;
    }
</style>
<script>
// @ is an alias to /src

export default {
  name: 'home'
}
</script>
