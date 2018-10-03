<template>
  <div class="container">
    <AppLogo/>
    <nuxt/>
  </div>
</template>

<script>
import AppLogo from "~/components/AppLogo.vue"

export default {
  components: {
    AppLogo
  }
}
</script>

<style lang="scss">

* {
  box-sizing: border-box;
  margin: 0;
  &:before, &:after{
    box-sizing: border-box;
    margin: 0;
  }
}

html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

body {
  background: linear-gradient(-140deg, #53AFAA 0%, #576B8A 100%);
  background-size: 100vw 100vh;
  background-attachment: fixed;
}

@media (min-width: 768px) {

  .container {
    grid-template-columns: repeat(12, [col-start] 1fr);
    grid-template-rows: auto 1fr;
    margin: 0 auto;
    grid-column-gap: 16px;
    display: grid;
    overflow-y: scroll;
    padding: 5rem 0;
  }

}
@media (max-width: 500px){
  .container {
    display: grid;
    grid-template-columns: repeat(4, [col] 1fr);
    grid-template-rows: auto 1fr;
    grid-column-gap: 1em;
    padding: 0 12px;


    }

  }

</style>
