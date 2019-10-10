<template>
  <q-page class="flex flex-center">
    
    <input v-model = "message"   @keyup = "handleKeyup"/>
    <button @click ="clearMessage">Reset</button>
  <H5 v-if="message.legth">{{message}} </H5>
  <H4 v-else>No Message</H4>

    <ul>
      <li v-for="task in tasks"
      :key="task.name">
      <div>{{task.name}}</div>
      <small>due {{task.dueDate}}
        at {{task.dueTime}}
      </small> 
      </li>
    </ul>

  </q-page>
</template>

<script>
export default {
 
data() {
    return {
    message:'Masukan Text',
    tasks: 
    [{
      name:"go to shop",
      dueDate:"2019/02/12",
      dueTime:"18.09"
     },
    {
      name:"get some fruits",
      dueDate:"2019/02/13",
      dueTime:"17.60"
    }]
    }
},
//menghapus menggunakan method
methods:
{
  clearMessage()
  {
    this.message=''
  },

  handleKeyup(e)
  {
    if (e.keyCode == 27)
    {
      this.message = 'ESC'
    }
  },
  uppercaseMessage()
  {
    return this.message.toUpperCase()
  }
}
}
</script>