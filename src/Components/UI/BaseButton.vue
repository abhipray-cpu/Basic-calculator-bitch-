<template>
<div :class="[type,btn_state]"  @click="clicked()">
    <h3>{{ text }}</h3>
</div>
</template>

<script>
//provide a slot for buttons in here
export default {
    data(){
        return{
            btn_state:'normal'
        }
    },
    props:['text','type'],
    methods:{
        clicked()
        {
             this.btn_state='pressed'
             setTimeout(() => this.btn_state='normal',250)
             
             
             
             
        }
    }
}

</script>

<style scoped>
.entry {
    border:1px solid black;
    
    border-radius:30px;
    width:100px;
    height:60px;
    margin-top:10px;
    margin-bottom: 10px;
    align-items: center;
    margin-left: 20px;
    
}


.entry h3{
        display: block;
   
    margin-block-start: 0em;
    margin-block-end: 0em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
    font-size: 34px;
    font-weight: bolder;
    text-align: center;
    margin-left:35px
}
.operator{
    border:1px solid black;
    
    border-radius:30px;
    width:100px;
    height:60px;
    margin-top:10px;
    margin-bottom: 10px;
    align-items: center;
    margin-left: 20px;
}
.operator h3{
    display: block;
     color:orangered;
    margin-block-start: 0em;
    margin-block-end: 0em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
    font-size: 34px;
    font-weight: bolder;
    text-align: center;
    margin-left:35px
}
.clear{border:1px solid black;
    box-shadow: 2px 2px 4px;
    border-radius:30px;
    width:100px;
    height:60px;
    margin-top:10px;
    margin-bottom: 10px;
    align-items: center;
    margin-left: 20px;}
.clear h3{display: block;
     color:red;
    margin-block-start: 0em;
    margin-block-end: 0em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
    font-size: 34px;
    font-weight: bolder;
    text-align: center;
    margin-left:35px
    }
   .x{border:1px solid black;
    box-shadow: 2px 2px 4px;
    border-radius:30px;
    width:100px;
    height:60px;
    margin-top:10px;
    margin-bottom: 10px;
    align-items: center;
    margin-left: 20px;}
   .x h3{
       display: block;
     color:orangered;
    margin-block-start: 0em;
    margin-block-end: 0em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
    font-size: 34px;
    font-weight: bolder;
    text-align: center;
    margin-left:35px
   } 
   .calculate{border:1px solid black;
    box-shadow: 2px 2px 4px;
    border-radius:30px;
    width:100px;
    height:60px;
    margin-top:10px;
    margin-bottom: 10px;
    align-items: center;
    margin-left: 20px;}
   .calculate h3{display: block;
     color:green;
    margin-block-start: 0em;
    margin-block-end: 0em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
    font-size: 34px;
    font-weight: bolder;
    text-align: center;
    margin-left:35px
    }
    .normal{box-shadow: 2px 2px 4px;}
.pressed{box-shadow: 0px 0px 0px;}
</style>