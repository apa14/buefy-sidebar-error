<template>
  <b-navbar class="is-primary" centered :mobile-burger="false" fixed-top>
    <template slot="brand">
      <div
        class="navbar-item"
        :style="{
          marginLeft: isOpenMenu ? '90px' : '0',
        }"
        @click="changeMenu"
      >
        <b-icon v-if="isOpenMenu" icon="menu-open" size="is-medium"> </b-icon>
        <b-icon v-else icon="menu" size="is-medium"> </b-icon>
      </div>
    </template>
    <template slot="end">
      <div class="navbar-item mr-3">
        <b-tooltip label="LogOut" position="is-left" type="is-light">
          <b-icon icon="logout"></b-icon>
        </b-tooltip>
      </div>
    </template>
  </b-navbar>
</template>
<script>
export default {
  data() {
    return {
      isOpenMenu: true,
    }
  },
  methods: {
    changeMenu() {
      this.$nuxt.$emit('changeMenu', !this.isOpenMenu)
      this.isOpenMenu = !this.isOpenMenu
    },
  },
}
</script>
