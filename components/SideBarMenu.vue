<template>
  <div class="sidebar-page">
    <section class="sidebar-layout">
      <b-sidebar
        mobile="reduce"
        expand-on-hover
        :fullheight="fullheight"
        :reduce="reduce"
        :open="isOpen"
      >
        <div class="p-1">
          <div class="block is-primary">
            <img
              src="https://raw.githubusercontent.com/buefy/buefy/dev/static/img/buefy-logo.png"
              alt="Lightweight UI components for Vue.js based on Bulma"
            />
            <div class="media">
              <div class="media-left center_userLogo">
                <figure class="image is-48x48">
                  <img
                    src="https://bulma.io/images/placeholders/96x96.png"
                    alt="Placeholder image"
                  />
                </figure>
              </div>
              <div class="media-content hover-user">
                <p class="title is-4">John Smith</p>
                <p class="subtitle is-6">@johnsmith</p>
              </div>
            </div>
          </div>
          <b-menu class="is-custom-mobile" :activable="false">
            <b-menu-list label="Usuario">
              <b-menu-item
                icon="account-box"
                size="is-medium"
                label="Profile"
                tag="nuxt-link"
                to="/"
              ></b-menu-item>
              <b-menu-item
                icon="logout"
                size="is-medium"
                label="LogOut"
                tag="nuxt-link"
                to="/"
              ></b-menu-item>
            </b-menu-list>
          </b-menu>
        </div>
      </b-sidebar>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: true,
      fullheight: true,
      reduce: true,
    }
  },
  created() {
    this.$nuxt.$on('changeMenu', (value) => {
      this.isOpen = value
    })
  },
}
</script>

<style lang="scss">
.p-1 {
  padding: 1em;
}
.sidebar-page {
  display: flex;
  flex-direction: column;
  width: 100%;
  min-height: 100%;
  // min-height: 100vh;
  .sidebar-layout {
    display: flex;
    flex-direction: row;
    min-height: 100%;
    // min-height: 100vh;
  }
}
.sidebar-content {
  background-color: white;
}
@media screen and (max-width: 1023px) {
  .b-sidebar {
    .sidebar-content {
      &.is-mini-mobile {
        &:not(.is-mini-expand),
        &.is-mini-expand:not(:hover) {
          .menu-list {
            li {
              a {
                span:nth-child(2) {
                  display: none;
                }
              }
              ul {
                padding-left: 0;
                li {
                  a {
                    display: inline-block;
                  }
                }
              }
            }
          }
          .menu-label:not(:last-child) {
            margin-bottom: 0;
          }
        }
      }
    }
  }
}
@media screen and (min-width: 1024px) {
  .b-sidebar {
    .sidebar-content {
      &.is-mini {
        &:not(.is-mini-expand),
        &.is-mini-expand:not(:hover) {
          .menu-list {
            li {
              a {
                span:nth-child(2) {
                  display: none;
                }
              }
              ul {
                padding-left: 0;
                li {
                  a {
                    display: inline-block;
                  }
                }
              }
            }
          }
          .menu-label:not(:last-child) {
            margin-bottom: 0;
          }
        }
      }
    }
  }
}
.mdi-36px.mdi::before {
  font-size: 24px;
}

.is-mini-expand:not(:hover) {
  .hover-user {
    display: none;
  }
}
.center_userLogo {
  margin-left: 0.1rem !important;
}
</style>
