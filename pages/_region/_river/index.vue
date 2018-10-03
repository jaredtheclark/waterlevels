<template>
  <section>
    <!-- <router-link :to="{ name: 'region', params: $route.river }"> Go Back</router-link> -->
    <div class="riverInfo">
      <p class="site-name">{{siteName}}</p>
      <p class="site-flow">
        {{flowAmount}}
        <span>{{flowUnit}}</span>
      </p>
    </div>
  </section>
</template>

<script>
import axios from 'axios'
import util from '~/assets/js/util'

export default {
  async asyncData ({ params }) {
      let { data } = await axios.get(`https://waterservices.usgs.gov/nwis/iv/?format=json&site=${params.river}`);

      let siteName = util.toTitleCase(data.value.timeSeries[0].sourceInfo.siteName),
          flowAmount = data.value.timeSeries[0].values[0].value[0].value,
          flowUnit = data.value.timeSeries[0].variable.unit.unitCode;


      return {
        data,
        siteName,
        flowAmount,
        flowUnit

      };
  }
}
</script>

<style lang="scss">
  .riverInfo{
    font-family:sans-serif;
  }
  section {
    grid-column: 1 / span 4;
  }
  .site-name{
    font-size: 2em;
    color: #F2F3F4;
    line-height: 1.4;
  }
  .site-flow {
    font-size: 1.25em;
    color: rgba(255,255,255,0.75);
    line-height: 1;
  }
</style>
