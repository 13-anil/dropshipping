<template>
  <div>
    <div class="product">
      <div class="img">
        <img src="../assets/router.png" >
      </div>
      <div class="info">
        <h1> {{ product }} </h1>
          <p v-if="!Sale"> onSale! </p>
        <h4> Description </h4>
          <ul>
            <li v-for="des in Description" :key="des.id"> {{ des }} </li>
          </ul>
        <p> Quantity </p>
        <input type="number" min="1"> <br>
        <button @click="addToCart()"> Add to Cart </button>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  data() {
    return {
      product: 'Router',
      Description: ['Brand: NetGear', 'Color: White', 'Price: 20€' ]
    }
  },
  sale: false,
  methods: {
      addToCart () {
      this.$emit('add-to-cart')
    }
  }
}
</script>

<style scoped>

  .product {
    display: flex;
    flex-flow: wrap;
    padding: 1rem;
  }

  img {
    border: 1px solid #d8d8d8;
    width: 60%;
    margin: 40px;
    box-shadow: 0px .5px 1px #d8d8d8;
  }

  .img, .info {
    display: inline-block;
    margin-top: 10px;
    width: 50%;
  }
</style>