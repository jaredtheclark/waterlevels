<template>
  <div class="main-select">
    <select v-model="state" name="state">
      <option disabled value="">Please select one</option>
      <option value="AL">Alabama</option>
      <option value="AK">Alaska</option>
      <option value="AZ">Arizona</option>
      <option value="AR">Arkansas</option>
      <option value="CA">California</option>
      <option value="CO">Colorado</option>
      <option value="CT">Connecticut</option>
      <option value="DE">Delaware</option>
      <option value="DC">District Of Columbia</option>
      <option value="FL">Florida</option>
      <option value="GA">Georgia</option>
      <option value="HI">Hawaii</option>
      <option value="ID">Idaho</option>
      <option value="IL">Illinois</option>
      <option value="IN">Indiana</option>
      <option value="IA">Iowa</option>
      <option value="KS">Kansas</option>
      <option value="KY">Kentucky</option>
      <option value="LA">Louisiana</option>
      <option value="ME">Maine</option>
      <option value="MD">Maryland</option>
      <option value="MA">Massachusetts</option>
      <option value="MI">Michigan</option>
      <option value="MN">Minnesota</option>
      <option value="MS">Mississippi</option>
      <option value="MO">Missouri</option>
      <option value="MT">Montana</option>
      <option value="NE">Nebraska</option>
      <option value="NV">Nevada</option>
      <option value="NH">New Hampshire</option>
      <option value="NJ">New Jersey</option>
      <option value="NM">New Mexico</option>
      <option value="NY">New York</option>
      <option value="NC">North Carolina</option>
      <option value="ND">North Dakota</option>
      <option value="OH">Ohio</option>
      <option value="OK">Oklahoma</option>
      <option value="OR">Oregon</option>
      <option value="PA">Pennsylvania</option>
      <option value="RI">Rhode Island</option>
      <option value="SC">South Carolina</option>
      <option value="SD">South Dakota</option>
      <option value="TN">Tennessee</option>
      <option value="TX">Texas</option>
      <option value="UT">Utah</option>
      <option value="VT">Vermont</option>
      <option value="VA">Virginia</option>
      <option value="WA">Washington</option>
      <option value="WV">West Virginia</option>
      <option value="WI">Wisconsin</option>
      <option value="WY">Wyoming</option>
    </select>
    <nuxt-link :to="`/${state}`" class="button main">See the Rivers</nuxt-link>
  </div>
</template>
<script>
export default {
  data() {
    return{
      state: ''
    }
  }
}

</script>
<style>
.main-select{
  display: flex;
  flex-direction: column;
  width: 100%;
  text-align: center;
}
select[name="state"]{
  -webkit-appearance: none;
  -moz-appearance: none;
  border:0;
  padding:1rem 1.25rem;
  background-color:hsla(194,68%,12%,0.2);
  border-radius:1.25rem;
  margin-bottom:1.5rem;
  color:#D8DDE2;
  text-align: center;

}
select[name="state"]:after{
  content:'';
  width:.5em;
  height:.5em;
  border-right:1px solid #CBD6E6;
  border-bottom:1px solid #CBD6E6;
  border-radius:.5px;
  transform:rotate(45deg);
}
.button.main{
  text-decoration: none;
  color:white;
  font-size:1rem;
  color:#D4E2E5;
  will-change: opacity;
  transition:opacity 300ms;
}
</style>
