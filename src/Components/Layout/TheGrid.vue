<template>
    <header>
        <h2>{{this.equation}}</h2>
    </header>
    <div>
         
        <base-button text="1"  type="entry" @click="addNumber(1)"></base-button>
        <base-button text="2"  type="entry" @click="addNumber(2)"></base-button>
        <base-button text="3"  type="entry" @click="addNumber(3)"></base-button>
        <base-button text="+"  type="operator" @click="addOperator('+')"></base-button>
        <base-button text="4"  type="entry" @click="addNumber(4)"></base-button>
        <base-button text="5"  type="entry" @click="addNumber(5)"></base-button>
        <base-button text="6"  type="entry" @click="addNumber(6)"></base-button>
        <base-button text="-"  type="operator" @click="addOperator('-')"></base-button>
        <base-button text="7"  type="entry" @click="addNumber(7)"></base-button>
        <base-button text="8"  type="entry" @click="addNumber(8)"></base-button>
        <base-button text="9"  type="entry" @click="addNumber(9)"></base-button>
        <base-button text="*"  type="operator" @click="addOperator('*')"></base-button>
        <base-button text="C"  type="clear" @click="Clear"></base-button>
        <base-button text="0"  type="entry" @click="addNumber(0)"></base-button>
        <base-button text="X"  type="x" @click="trim_last"></base-button>
        <base-button text="%"  type="operator" @click="addOperator('%')"></base-button>
        <base-button text="."  type="entry" @click="addNumber('.')"></base-button>
        <base-button text="="  type="calculate" @click="Calculate"></base-button>
        <base-button text="e"  type="entry" @click="addNumber(2.71)"></base-button>
        <base-button text="/"  type="operator" @click="addOperator('/')"></base-button>
        
        
        
    </div>
</template>


<script>
import BaseButton from '../UI/BaseButton.vue'

export default {
    components:{
        'base-button':BaseButton,
    },
    provide(){
        return{
            value:this.equation
        }
    },
    data(){
        return{
            equation:''
        }
    },
    
    methods:{
        addNumber(number){
            this.equation+=number;
            
            
            
           
        }
        ,addOperator(operator) {
            this.equation+=operator;
            
            
            
    },
    trim_last(){
             this.equation=this.equation.slice(0,-1)
             
    },
    Calculate()
    {
         this.equation=eval(this.equation)
    },
    Clear(){
        this.equation=''
        
    },

  //use this for key binding this does work
  doCommand(e) {
       
		let cmd = String.fromCharCode(e.keyCode).toLowerCase();
       
       
        if(cmd in ['1','2','3','4','5','6','7','8','9','0','+','-','*','/','%'] || cmd ==='+' || cmd ==='-' || cmd ==='*' || cmd ==='/' || cmd ==='%' || cmd ==='.')
        {
		this.equation+=cmd;
    
        }
        else if(e.key === 'Enter')
         {
             this.Calculate()
         }
	}
    
   
    }
    ,created() {
	window.addEventListener('keypress', this.doCommand);

    
},
unmounted() {
	window.removeEventListener('keypress', this.doCommand);
}


}
</script>

<style scoped>
div{
    display: grid;
    grid-template-columns: 20fr 20fr 20fr 20fr;
}
header{
    margin-top:2px;
    margin-bottom:10px;
    color:orangered;
    font-weight: bolder;
    border:2px solid black;
    width:600px;
    height:40px;
    padding:10px
}
</style>