<template>
  <div>
    <SideBarMenu />
    <section
      class="main-content columns"
      :style="{
        marginLeft: isMenuOn ? '80px' : '0',
      }"
    >
      <NavBarMenu />
      <div class="container column is-10">
        <nuxt />
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMenuOn: true,
    }
  },
  created() {
    this.$nuxt.$on('changeMenu', (value) => {
      this.isMenuOn = value
    })
  },
}
</script>
