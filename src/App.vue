<template>
    <div>
        <app-header/>
        <div class="container">

          <transition name="slideup">
            <div class="p-3 mb-2 bg-success text-white" v-if="display">Hello</div>
           </transition>


           <transition name="appear">
            <div class="p-3 mb-2 bg-success text-white" v-if="display">Hello</div>
           </transition>

          <button class="btn btn-primary" @click="display = !display">Toggle Anim</button>

        </div>
        <app-footer/>
    </div>
</template>

<script>
    
    export default {
        data(){
            return {
              display: false,
            }
        }
    }
</script>


<style>

    .appear-enter{
      transform: translateX(50px);
      opacity: 0;
    }

    .appear-enter-active{
      transition: all .5s ease;
    }

    .appear-leave{
    
    }
      
    .appear-leave-active{
       
    }

    .slideup-enter{
        opacity: 0;
      
    }

    .slideup-enter-active{
      transition: opacity 1s;
      animation: slideUp 1s ease-out;
    }

    .slideup-leave{
    
    }
      
    .slideup-leave-active{
      opacity: 0;
      transition: opacity 1s;
      animation: slideDown 1s ease-out;
    }

    @keyframes slideUp{
      from{
        transform: translateY(30px);
      }
      to{
        transform: translateY(0);
      }
    }

    @keyframes slideDown{
      from{
        transform: translateY(0);
      }
      to{
        transform: translateY(30px);
      }
    }


    body {
        padding:0;
        margin:0;
        font-family: 'Roboto', sans-serif;
    }

    .container {
        min-height: 84vh;
        box-sizing: border-box;
        padding: 20px;
    }



</style>