<template>
  <section class="section">
    <div class="card block">
      <div class="card-content">
        <div class="content">
          <h1 class="title is-2">CM to Inch converter</h1>
          <b-field label="In Centimeter">
            <b-input v-model="centimeter"  lazy  type="number" @blur="$router.push(`/${centimeter}`)" ></b-input>
          </b-field>
          <b-field label="">
            <b-slider
              :value="centimeter"
              lazy
              indicator
              :tooltip="false"
              :max="10000"
              @change="$router.push(`/${$event}`)"
            ></b-slider>
          </b-field>
          <h2 class="title is-3">{{ inches.toFixed(3) }} {{(inches>=2)?'inches':'inch'}}</h2>
            <b-button type="is-primary" @click="centimeter=null">Clear</b-button>
        </div>
      </div>
    </div>
    <div class="columns">
      <div class="column">
        <div class="card min-height-450">
          <div class="card-content">
            <div class="content">
              <h1 class="title is-3">How to Convert Centimeter to Inches</h1>

              <p>The first thing you need to know before getting into the calculations is, there are 2.54 centimeters in one inch. This is how the equation looks like.</p>
              <p>{{ centimeter}}cm = {{centimeter}}/2.54 ″ = {{(centimeter/2.54).toFixed(2)}}″</p>
              <p>There’s of course a way to reconvert. You can just multiply the cm figure by 0.3937. Here’s the equation:</p>
              <p>Inches = cm × 0.3937</p>
              <h2 class="title is-3">{{ inches.toFixed(3) }} {{(inches>=2)?'inches':'inch'}}</h2>

            </div>
          </div>
        </div>
      </div>
      <div class="column">
        <div class="card min-height-450">
          <div class="card-content">
            <div class="content">
              <h1 class="title is-3">The Formula</h1>
              <p>
                There’s a simple formula that’ll allow you to convert any centimeter distance to inches instantly. As we know:
              </p>

              <p>1 cm = 0.3937007874 in</p>
              <p>So, suppose we’re willing to convert 15 cm to inches. Then the calculation will be like this:</p>
              <p>15 cm = 15 × 0.3937007874 inches = 5.905511811 inches</p>
              <p>So, the distance conversion formula would be:</p>
              <p>d <sub>(cm)</sub> = (d × 0.3937007874) <sub>(inch)</sub></p>


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
                <strong>Definition: </strong>A centimeter, symbolically known as cm, is a unit length that’s recognized by the System of Units or SI. This is current accepted form of the metric system. There are 100 cm in a meter in total. A centimeter can be defined as 1/100 meter.
              <p>
                <strong>History/origin: </strong>The prefix “centi” used in centimeter refers to the fact that it’s equal to one hundredth of a meter. Based on a decimal system, metric prefixes can range from all the way to 10-18 to 1018 . The base is considered to be meter and it has no prefixes. In other words, meter has a factor of 1.
              </p>
              <p>Kilo-, mega- giga- mili-, nano-, and other prefixes can prove to be helpful while wanting to quickly convert and navigate through metric units.</p>
              <p>
                <strong>Current usage: </strong>In the worldwide countries that have undergone metrication, cm is used all the time. It’s commonly used whenever a smaller denomination of meter is necessary. The human height is commonly measures in centimeters as well (Outside countries like the US).
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
                <strong>Definition: </strong>Just like the centimeter, inch, symbolically recognized as in, is also a unit of length. But unlike cm, inch falls under the US customary systems of measurement. In 1959, an inch was defined to be equivalent to 2.54 millimeters.
              </p>
              <span>Note: A foot consists of 12 inches and there are 36 inches in a yard.</span>
              <p>
                <strong>History/origin: </strong>If we go back to the source, inch originally came from the word “uncia.” It equated to the one twelfth of the Roman foot. Apart from the various standards of the inch in the past, the current definition stands on the international yard measurement.
              </p>
              <p>The earliest measurement of inch was based on barleycorns. Interestingly, an inch was equal to the exact lengthy of three grains of round, dry barley placed from end-to-end. Yet another instance of inch was measured by the width of human thumbs. </p>
              <p>This length was averaged by the width of three thumbs (A small, medium, and large one). </p>
              <p>
                <strong>Current usage: </strong>Inches are generally used in the United States, the UK, and Canada. Japan uses it too in occasions of electronic parts like the size of display screens. This is done similarly in other countries as well.
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
              <h2 class="title is-3">FAQ</h2>
              <h3>Is it possible to reconvert inches to centimeter?</h3>
              <p>
               Yes, after you’ve converted to inches, all you have to do is multiply the cm distance by 0.3937. This should return the figure back in inches.
              </p>
              <h3>How many centimeters are there in an inch?</h3>
             <p>
                To be exact, there are 2.54 centimeters in an inch. This should answer it better: 1 in = 2.54×1in = 2.54cm
              </p>
              <h3>Should I measure with cm or inches?</h3>
              <p>This entirely depends on the common preference that’s accepted in your area. Be it metric or imperial units, rest assured they can be converted and reconverted. </p>


            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- <div class="container">
          <b-table :data="chartData" :columns="columns"></b-table>
    </div> -->
    <quick-links :centimeter="Number(centimeter)"></quick-links>
  </section>
</template>

<script>
export default {

  name: 'HomePage',

  components: {},
  asyncData({isDev, route, store, env, params, query, req, res, redirect, error}) {
    const centimeter = Number(route.params.cm);
    const title= `${centimeter} to inch`;

    return {centimeter, title}
  },

  data() {
    return {

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
  head(){
    return {
      title: `${this.centimeter} cm to inch`
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
<style>
  .min-height-450 {
    min-height: 450px;
  }
</style>
