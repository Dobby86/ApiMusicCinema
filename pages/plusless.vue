<template>
<div class="calcolo row">

        <div class="col-6">
            <button @click="metti('+')" style="font-size:30px; padding:15px">+</button>
        </div>
        <h2 style="font-size:50px">{{ conto }}</h2>

        <h2 :style="styleCss()">{{ limit() }}</h2>
        

        <div class="col-6">
            <button @click="togli('-')" style="font-size:30px; padding:15px">-</button>
        </div>
       

   
</div>

   
</template>
<script>
export default {
  data(){
      return{
          conto: "0" ,
          min: "MINORE",
          max:"MAGGIORE",
          numero :0                     
      }
            
  },
  mounted:function(){
      console.log("MONTATO");
      this.conto = 0;
  },
  computed : {
    
   } ,   
  methods: {
      limit: function(){
        if(this.conto <= 0){
            return this.min
            
            
        }else{
            return this.max
        }
    },
      styleCss(){
          if(this.conto > this.numero ){
            return {
                'color': 'green',
               'background': 'lightgreen'
            }
            
        }else{
            return {
                'color': 'red',
                'background': 'salmon'
            }
        }
      },
   mettiTogliSpunta(){
          
           var ctrl = $(this).find("i");
            if (ctrl.hasClass("fa fa-child")){
                ctrl.attr("class","fa fa-cc");
            }else{
                ctrl.attr("class", "fa fa-cloud-download");
            }
            
        },
        metti(ops){
            if(ops == '+'){
                this.conto++
                console.log("+");
            }
        },
        togli(ops){
            if(ops == '-'){
                this.conto--
                console.log("-");
            }
        }
        
      }
      }
      </script>

      <style scoped>
      .calcolo{
          min-height: 50vh;
      }
      </style>