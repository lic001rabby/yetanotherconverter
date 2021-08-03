<template>
  <section class="section">
    <div class="card block">
      <div class="card-content">
        <div class="content">
          <h1 class="title is-2">Inch to Centimeter</h1>
          <b-field label="In inch">
            <b-input v-model="inches" type="number" value="0"></b-input>
          </b-field>
          <b-field label="">
            <b-slider
              v-model="inches"
              lazy
              indicator
              :tooltip="false"
              :max="10000"

            ></b-slider>
          </b-field>
          <h2 class="title is-3">{{ centimeter.toFixed(3) }} centimeters</h2>
        </div>
      </div>
    </div>
    <div class="columns">
      <div class="column">
        <div class="card">
          <div class="card-content">
            <div class="content">
              <h1 class="title is-3">How it works</h1>
              <p>
                There are {{ inchPerCm }} inches per centimeter and there are
                {{ cmPerInch }}
                centimeters per inch. Therefore, you can get the answer to "{{
                  inches
                }}
                inchs in centimeters?" in two different ways. You can either
                multiply {{ inches }} by {{ cmPerInch }} or divide
                {{ inches }} by {{ inchPerCm }}. Here is the math to get the
                answer by multiplying {{ inches }} inches by {{ cmPerInch }}.
              </p>
              <h2 class="title is-3">{{ centimeter.toFixed(2) }}</h2>
            </div>
          </div>
        </div>
      </div>
      <div class="column">
        <div class="card">
          <div class="card-content">
            <span class="is-4">Space for ad</span>
          </div>
        </div>
      </div>
      <div class="column">
        <div class="card">
          <div class="card-content">
            <span class="is-4">Space for content</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HomePage',

  components: {},
  data() {
    return {
      inches: 0,
      cmPerInch: 2.54,
      inchPerCm: 0.3937008,
    }
  },
  computed: {
    centimeter() {
      if (this.inches === 0) return 0
      return this.inches * this.cmPerInch
    },
  },
}
</script>
