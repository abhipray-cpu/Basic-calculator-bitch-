<template>
    <div id="layout">
      <the-header></the-header>
      
      <the-grid></the-grid>
    </div>
</template>

<script>
import TheHeader from './TheHeader.vue'

import TheGrid from './TheGrid.vue'

export default ({
    components:{
        TheHeader,
       
        TheGrid
    }
})
</script>

<style scoped>
#layout {
    width:fit-content;
    margin-left:25%;
    margin-top:5%;
    border:2px solid black;
    height:fit-content;
    max-height: 1000px;
}
</style>