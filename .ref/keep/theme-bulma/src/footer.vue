<template>
  <footer class="footer">
    <div class="container footer-top">
      <div class="columns is-tablet">
        <div class="column">
          <h4 class="menu-label menu-label-indent">
            {{ setting("footer.nav1Headline") }}
          </h4>

          <ul class="menu-list">
            <template v-for="(item, index) in setting('footer.nav1')">
              <li :key="index">
                <factor-link :path="item.path" class="navbar-item">
                  <span>{{ item.name }}</span>
                </factor-link>
              </li>
            </template>
          </ul>
        </div>
        <div class="column">
          <h4 class="menu-label menu-label-indent">
            {{ setting("footer.nav2Headline") }}
          </h4>
          <ul class="menu-list">
            <template v-for="(item, index) in setting('footer.nav2')">
              <li :key="index">
                <factor-link :path="item.path" class="navbar-item">
                  <span>{{ item.name }}</span>
                </factor-link>
              </li>
            </template>
          </ul>
        </div>
        <div class="column">
          <h4 class="menu-label menu-label-indent">
            {{ setting("footer.nav3Headline") }}
          </h4>
          <ul class="menu-list">
            <template v-for="(item, index) in setting('footer.nav3')">
              <li :key="index">
                <factor-link :path="item.path" class="navbar-item">
                  <span>{{ item.name }}</span>
                </factor-link>
              </li>
            </template>
          </ul>
        </div>
        <div class="column is-5">
          <h4 class="menu-label">{{ setting("footer.socialHeadline") }}</h4>

          <template v-for="(item, index) in setting('footer.social')">
            <factor-link
              :key="index"
              :path="item.path"
              class="navbar-item is-inline-block"
              target="_blank"
            >
              <factor-icon v-if="item.icon" :icon="item.icon" />
            </factor-link>
          </template>

          <h4 class="menu-label">{{ setting("footer.subscribeHeadline") }}</h4>
          <component :is="setting(`footer.subscribe`)" />
        </div>
      </div>
    </div>
    <div class="container">
      <div class="columns">
        <div class="column">
          <hr />
        </div>
      </div>
    </div>
    <div class="container footer-bottom">
      <div class="columns">
        <div class="column is-2 has-text-centered-mobile has-text-left-desktop">
          <factor-link path="/" class="footer-logo">
            <component :is="setting(`footer.logo`)" />
          </factor-link>
        </div>
        <div class="column has-text-centered-mobile has-text-right-tablet is-size-7">
          <div v-formatted-text="setting('footer.legal')" class="copyright" />
          <div class="terms">
            <template v-for="(item, index) in setting('footer.terms')">
              <factor-link :key="index" :path="item.path">{{ item.text }}</factor-link>
            </template>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>
<script>
import { factorLink } from "@factor/ui"
import { setting } from "@factor/tools"
export default {
  components: { factorLink },
  methods: { setting }
}
</script>

<style lang="less">
.footer {
  .footer-top {
    .menu-label-indent {
      padding-left: 1em;
      padding-right: 1em;
    }
  }
  .footer-logo {
    svg {
      width: 34px;
      opacity: 0.2;
    }
  }
  .copyright {
    padding-bottom: 0.5em;
  }
  .terms {
    a {
      display: inline-block;
      padding-left: 10px;
    }
  }
}
</style>
