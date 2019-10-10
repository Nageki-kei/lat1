<template>
  <q-page class="flex flex-center">
    
    <input v-model = "message"   @keyup = "handleKeyup"/>
    <button @click ="clearMessage">Reset</button>
 <H5> {{message}} </H5>
  </q-page>
</template>

<script>
export default {
 
data(){
  return{
  message: 'Masukan Text'
}
},

//menghapus menggunakan method
methods:{
  clearMessage(){
    this.message=''
  },

handleKeyup(e){
  if (e.keyCode == 27){
    this.message = 'ESC'
  }
}
}
}
</script>