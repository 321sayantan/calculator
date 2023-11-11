<template>
    <div class=" container mx-auto">
        <div class="input rounded">
            {{calculatorValue || 0}}
        </div>
        <div class="row key m-auto p-1">
            <div class="col-3 btn hover" v-for="n in calElements" :key="n"
            :class="{'bg-orange': n=='=', 'bg-blue': ['AC','C','%','/','*','-','+'].includes(n)}" 
                @click="action(n)">
                {{n}}                
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'calculator',
    data(){
        return{
            calculatorValue: '',
            calElements: ['AC','C','%','/','7','8','9','*','4','5','6','-','1','2','3','+','0','00','.','='],
            operator: ['AC','C','%','/','*','-','+','.']
        }
    },
    methods:{
        action(n){
            // var lastval = this.calculatorValue.slice(-1);
            // console.log(lastval)
            // if(this.operator.includes(lastval) && this.operator.includes(n))
            // {}
            // else

             if(n!='AC' && n!='C' && n!='='){
                this.calculatorValue = this.calculatorValue + n;
            }

            if(n == 'AC')
                this.calculatorValue = '';
            if(n == 'C')
                this.calculatorValue = this.calculatorValue.slice(0, -1);
            try{
            if(n =='=')
                this.calculatorValue = eval(this.calculatorValue);
            }
            catch(err){
                this.calculatorValue = 'Syntax Error'
            }

            if(n==='%')
                this.calculatorValue = parseFloat(this.calculatorValue)/100;            
        }
    }
}
</script>

<style scoped>

.container{
    width: 350px;
    height: 500px;
    padding-top: 10px;
    background-color: rgb(84, 190, 247);
    border-radius: 20px;
    border: 3px solid black;
    /* backdrop-filter: blur(0px); */
    box-shadow: 0px 0px 13px 7px black;
}
.input{
    height: 70px;
    margin: 10px 0px;
    text-align: right;
    padding-top: 20px;
    padding-right: 8px;
    font-size: 37px;
    overflow: hidden;
    border: 1px solid black;
    background: #fff;
    box-shadow: 0px 0px 6px 2px black;
}
.btn{
    margin: 5px 8px;
    padding: 15px 0px;
    width: 61px;
    border-radius: 100%;
    font-size: 20px;
    font-weight: 500;
}
.hover:hover{
    background-color: rgb(52, 184, 255);
    /* scale: 0.95; */
}
.hover:active{
    /* background-color: rgb(52, 184, 255); */
    scale: 0.95;
    box-shadow: 0px 0px 10px black;
}
.bg-orange{
    background-color: orangered;
}
.bg-blue{
    background-color: rgb(17, 168, 250);
}
</style>