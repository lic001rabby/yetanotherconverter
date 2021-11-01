<template>
  <div id="quicklinks">
    <div class="card">
          <div class="card-content">
            <div class="content">
              <h2 class="title is-3">Related conversions</h2>
              <div class="flex-container" style="display:flex; flex-direction:column">
                <span style="margin-left:5px " v-for="i in 9" :key="i">
                   <nuxt-link :to="`/${centimeter+i}`"> {{`${centimeter+i}cm`}} to inch </nuxt-link>
                </span>
              </div>



            </div>
          </div>
        </div>
  </div>
</template>

<script>
export default {
  props: {
    centimeter: {
      type: Number,
      default: 1
    }
  }
}
</script>
