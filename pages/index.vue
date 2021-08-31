<template>
  <section class="section">
    <div class="card block">
      <div class="card-content">
        <div class="content">
          <h1 class="title is-2">CM to Inch converter</h1>
          <b-field label="In Centimeter">
            <b-input v-model="centimeter" type="number" value="0"></b-input>
          </b-field>
          <b-field label="">
            <b-slider
              v-model="centimeter"
              lazy
              indicator
              :tooltip="false"
              :max="10000"
            ></b-slider>
          </b-field>
          <h2 class="title is-3">{{ inches.toFixed(3) }}</h2>
            <b-button type="is-primary" @click="centimeter=null">Clear</b-button>
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
                  centimeter
                }}
                centimeters in inches?" in two different ways. You can either
                multiply {{ centimeter }} by {{ inchPerCm }} or divide
                {{ centimeter }} by {{ cmPerInch }}. Here is the math to get the
                answer by dividing {{ centimeter }} centimeters by
                {{ inchPerCm }}.
              </p>
              <h2 class="title is-3">{{ inches.toFixed(3) }}</h2>

            </div>
          </div>
        </div>
      </div>
      <div class="column">
        <div class="card">
          <div class="card-content">
            <div class="content">
              <h1 class="title is-3">How it works</h1>
              <p>
                There are {{ inchPerCm }} inches per centimeter and there are
                {{ cmPerInch }}
                centimeters per inch. Therefore, you can get the answer to "{{
                  centimeter
                }}
                centimeters in inches?" in two different ways. You can either
                multiply {{ centimeter }} by {{ inchPerCm }} or divide
                {{ centimeter }} by {{ cmPerInch }}. Here is the math to get the
                answer by dividing {{ centimeter }} centimeters by
                {{ inchPerCm }}.
              </p>
              <h2 class="title is-3">{{ inches.toFixed(3) }}</h2>

            </div>
          </div>
        </div>
      </div>


    </div>
    <div class="columns">

      <div class="column">
        <div class="card">
          <div class="card-content">
            <div class="content">
              <h2 class="title is-3">Centimeter</h2>
              <p>
                <strong>Definition: </strong>A centimeter (symbol: cm) is a unit of length in the International System of Units (SI), the current form of the metric system. It is defined as 1/100 meters.
              </p>
              <p>
                <strong>History/origin: </strong>A centimeter is based on the SI unit meter, and as the prefix "centi" indicates, is equal to one hundredth of a meter. Metric prefixes range from factors of 10-18 to 1018 based on a decimal system, with the base (in this case the meter) having no prefix and having a factor of 1. Learning some of the more commonly used metric prefixes, such as kilo-, mega-, giga-, tera-, centi-, milli-, micro-, and nano-, can be helpful for quickly navigating metric units.
              </p>

            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="columns">

      <div class="column">
        <div class="card">
          <div class="card-content">
            <div class="content">
              <h2 class="title is-3">Inch</h2>
              <p>
                <strong>Definition: </strong>An inch (symbol: in) is a unit of length in the imperial and US customary systems of measurement. An inch was defined to be equivalent to exactly 25.4 millimeters in 1959. There are 12 inches in a foot and 36 inches in a yard.
              </p>
              <p>
                <strong>History/origin: </strong>The term "inch" was derived from the Latin unit "uncia" which equated to "one-twelfth" of a Roman foot.
              </p>

            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="container">
          <b-table :data="chartData" :columns="columns"></b-table>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HomePage',

  components: {},
  data() {
    return {
      centimeter: 0,
      cmPerInch: 2.54,
      inchPerCm: 0.3937008,
      chartData: [
        {cm:0.01, inch:0.0039370079}, {cm: 0.1, inch:0.0393700787}
      ],
      columns: [
        {
          field: 'cm',
          label: 'Centimeter',

          numeric: true,
        },
        {
          field: 'inch',
          label: 'Inch',

          numeric: true,
        }
      ]
    }
  },
  computed: {
    inches() {
      if (this.centimeter === 0) return 0
      return this.centimeter / this.cmPerInch
    },
  },
}
</script>
