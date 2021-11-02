<template>
  <div>

    <b-navbar class="is-primary">
        <template #brand>
            <b-navbar-item tag="router-link" :to="{ path: '/' }">
                <a style="color:#fff;" class="navbar-item title is-4 has-text-weight-bold" href="/">
          CM to Inch
        </a>
            </b-navbar-item>
        </template>
        <template #start>
            <b-navbar-item href="/">
                Home
            </b-navbar-item>

        </template>

    </b-navbar>

    <section class="main-content columns">


      <div class="container column is-10">
        <Nuxt />
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          title: 'Home',
          icon: 'home',
          to: { name: 'index' },
        },

      ],
    }
  },
}
</script>
