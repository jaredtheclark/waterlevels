<template>
  <section>
    <div>
      <stateSelect/>
      <nuxt/>
    </div>
  </section>
</template>

<script>
import axios from 'axios'
import stateSelect from '~/components/stateSelect.vue'

export default {
  components: {
    stateSelect
  }
}
</script>

<style scoped="true">

.container > * {
    width: 100%;
    justify-items:center;
}

.container > div {
  grid-column: 2 / span 2;
  padding: 0 1.5rem;
}

.container > section {
  grid-column: span 4;
}

</style>
