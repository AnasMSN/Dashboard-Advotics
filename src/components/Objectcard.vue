<template>
  <div>
    <div class="row product">
        <div class="col-4">
            <img src="https://media-exp1.licdn.com/dms/image/C561BAQEFU2TIVDXUFA/company-background_10000/0?e=2159024400&v=beta&t=IsWUNq6keGlPZI8GAniAEzihI87FrbZr2ybpVOxUlXA" 
                alt="mcflurry" class="img-fluid">
        
        </div>

        <div class="col-8">
            <div class="row">
                <div class="col-12">[Nama Produk]</div>
                <div class="col-7">Rp XX</div>
                <div class="col-5">[Jml]</div>
            
            </div>
        
        </div>

    </div>
  </div>
  
</template>

<script>
export default {
  name: 'Objectcard',
  props: ["image_url", "name", "price", "total"],
  data() {
      return {

      }
  }
}
</script>

<style scoped>

div {
    font-size: 15px;
}

.product {
    border-style: solid;
    border-width: 1px;
    border-color:beige;
    padding: 0;
}

</style>
