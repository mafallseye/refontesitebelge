<template>
  <div class="d-flex justify-content-center spin" v-if="isLoading">
  <div class="spinner-border" role="status">
    <span class="visually-hidden">Loading...</span>
  </div>
</div>

<div v-else>

    <InfoBelge />
</div>
</template>
<script>
import InfoBelge from "@/components/InfoBelge.vue";
export default{
components:{
    InfoBelge
},
data(){
    return{
        isLoading :true
    }
},
mounted () {
    setTimeout(() => {
      this.isLoading = false
    }, 1000)
  }
}
</script>
<style scoped>
.spin{

padding-top: 25%;

}
</style>