<template>
  <div class="p-2 d-flex justify-content-between align-items-center">
    <div class="d-flex align-items-center">
      <div class="image-container">
        <img :src="item.product.image" class="img-fluid">
      </div>
      <div>
        <div><strong>{{ item.product.name }}</strong></div>
        <div><small>{{ item.quantity }} x {{ item.product.price }}</small></div>
      </div>
    </div>
    <div>
      <div class="btn-group btn-group-sm me-2">
        <button class="btn btn-dark " v-on:click.stop =removeItem(item) >-</button>
        <button class="btn btn-dark" v-on:click.stop =addItem(item) >+</button>
      </div>
      <button class="btn btn-danger btn-sm"><i class="fa-solid fa-trash"></i></button>
    </div>
  </div>
</template>

<script>

export default {
  props: ['item'],
  methods{
    
  }
 
  
}

</script>

<style scoped>
  .image-container {
    width: 90px;
  }
</style>