<template>
  <div class="v-cart-item">
    <img :src="require('../assets/images/' + cart_item_data.image)" alt="img" />
    <div class="v-cart-item__info">
      <p>{{ cart_item_data.name }}</p>
      <p>{{ cart_item_data.price }}</p>
      <p>{{ cart_item_data.article }}</p>
    </div>
    <div class="v-cart-item__quantity">Qnt:{{ cart_item_data.quantity }}</div>
    <button @click="deleteFromCart">Delete</button>
  </div>
</template>

<script>
export default {
  name: "v-cart-item",
  props: {
    cart_item_data: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  data() {
    return {}
  },
  computed: {},
  methods: {
    deleteFromCart() {
      this.$emit('deleteFromCart')
    }
  },
  mounted() {
    this.$set(this.cart_item_data, 'quantity' ,1)
  }
}
</script>

<style lang="scss">
    // .v-cart-item {
    //     display: flex;
    //     flex-wrap: nowrap;
    //     align-items: center;
    //     justify-content: space-between;
    //     flex-basis: 25%;
    //     box-shadow: 0 0 8px 0 #e0e0e0;
    //     padding: $padding * 2;
    //     margin-bottom: $margin * 2;}
        .v-cart-item {
          border-radius: 5px;
          padding: 20px;
          background: white;
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          position: relative;
        }
</style>