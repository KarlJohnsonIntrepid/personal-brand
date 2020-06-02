<template>
  <div>
    <nav
      class="navbar header has-shadow is-primary"
      role="navigation"
      aria-label="main navigation"
    >
      <div class="navbar-brand">
        <a class="navbar-item">
          <h2>Karl Johnson</h2>
          - Web Application Development Expert
        </a>
      </div>

      <div class="navbar-end">
        <a class="navbar-item">
          <img
            src="https://bulma.io/images/bulma-logo.png"
            width="112"
            height="28"
            alt="Bulma"
          />
        </a>
      </div>
    </nav>

    <section class="main-content columns">
      <aside class="column  is-12-tablet is-4-desktop is-3-widescreen section">
        <b-menu>
          <b-menu-list>
            <b-menu-item :active="isActive" icon="account" expanded>
              <template slot="label" slot-scope="props">
                Karl Johnson
                <b-icon
                  :icon="props.expanded ? 'menu-down' : 'menu-up'"
                  class="is-pulled-right"
                ></b-icon>
              </template>
              <nuxt-link
                :to="item.to"
                v-for="(item, key) of about"
                :key="key"
              >
                {{ item.title }}
              </nuxt-link>
            </b-menu-item>

            <b-menu-item icon="settings">
              <template slot="label" slot-scope="props">
                Architecture and Design
                <b-icon
                  :icon="props.expanded ? 'menu-down' : 'menu-up'"
                  class="is-pulled-right"
                ></b-icon>
              </template>
              <nuxt-link
                :to="item.to"
                v-for="(item, key) of architecture"
                :key="key"
              >
                {{ item.title }}
              </nuxt-link>
            </b-menu-item>

            <b-menu-item icon="settings">
              <template slot="label" slot-scope="props">
                AEM
                <b-icon
                  :icon="props.expanded ? 'menu-down' : 'menu-up'"
                  class="is-pulled-right"
                ></b-icon>
              </template>
              <nuxt-link :to="item.to" v-for="(item, key) of aem" :key="key">
                {{ item.title }}
              </nuxt-link>
            </b-menu-item>
          </b-menu-list>
        </b-menu>
      </aside>

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
      isActive: true,
      about: [
        {
          title: 'About / CV',
          to: { name: 'index' },
        }
      ],
      architecture: [
        {
          title: 'How to architect a blog for free',
          to: { name: 'architecture-how-i-architected-this-site-for-free' }
        },
        {
          title: 'DRY is a lie',
          to: { name: 'architecture-dry-is-a-lie' }
        }
      ],
      aem: [
        {
          title: 'AEM',
          to: { name: 'aem-aem' }
        }
      ]
    }
  }
}
</script>

<style lang="scss">
@import '../assets/sass/bulma_overrides';

@media screen and (max-width: 1024px) {
  .main-content {
    display: flex;
    flex-direction: column-reverse;
  }
}
</style>
