<template>
  <div>
    <NuxtLink to="/nav">
        Go to Nav
    </NuxtLink>
    <NuxtLink to="/">
        Go to home
    </NuxtLink>
    <button @click="toggle">Toggle</button>
    <button @click="reset">Reset</button>
    <div v-if="isToggle">
      12132
    </div>
    <div v-else>
      <ul>
        <li v-for="item in items" :key="item">
          <SfProductCard
            :title="`title ` + item"
            image="https://docs.storefrontui.io/assets/storybook/Home/productB.jpg"
            max-rating="5"
            image-width="100%"
            image-height="400"
            class="sw-product-card"
          />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import {SfProductCard} from '@storefront-ui/vue';
export default {
  name: 'IndexPage',
  components: {
    SfProductCard
  },
  data () {
    return {
      isToggle: true,
      items: 1000
    }
  },
  methods: {
    toggle () {
      this.isToggle = !this.isToggle
    },
    reset () {
      this.items = 1;
    },
    loadmore() {

    }
  }
}
</script>
<style>
  ul {
    display: flex;
    flex-wrap: wrap;
  }
  li {
    width: 25%;
  }
</style>
