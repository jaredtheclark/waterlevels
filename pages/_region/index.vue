<template>
<section>
  <div>
    <nuxt />
    <p>Rivers in {{region}}</p>
    <ul class="riversList">
      <li v-for="(site, index) in sites" :key="index">
        <router-link :to="{ name:'region-river', params: { river: site.sourceInfo.siteCode[0].value } }">
          {{ site.sourceInfo.siteName }}
        </router-link>
      </li>
    </ul>
  </div>
</section>
</template>

<script>
import axios from 'axios'
import AppLogo from '~/components/AppLogo.vue'

export default {
  components: {
    AppLogo
  },
  async asyncData({ params }) {

    let { data } = await axios.get(`https://waterservices.usgs.gov/nwis/iv/?format=json&parameterCd=00065&stateCD=${params.region}`);
    let  siteRegion = data.value.queryInfo.note[0].value.valueOf(),
        region = siteRegion[1] + siteRegion[2]

    return {
      sites: data.value.timeSeries,
      region
    };
    //console.log(siteId)
  }
}
</script>

<style>
section {
  grid-column: 1 / span 4;
}
section>div>p {
  color: #D5D5D5;
  text-align: left;
  width: 100%;
  padding-left: 12px;
  font-size: 10px;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.riversList {
  list-style: none;
  padding: 0;
  width: 100%;
}

.riversList li {
  font-size: 0.875rem;
}

.riversList a {
  text-decoration: none;
  color: #D8DDE2;
  padding: 12px;
  display: block;
  border-radius: 1rem;
}

.riverList a:hover {
  background-color: rgba(10, 26, 31, 0.20);
}
</style>
