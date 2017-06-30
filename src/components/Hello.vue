<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>  
    <input type="" name="" v-model="newItem" v-on:keyup.enter="addNew">
    <ul>
        <li v-for="item in items" v-bind:class={finished:item.isFinished} v-on:click="toggleFinish(item) ">
            {{item.label}} 
        </li>
    </ul>
  </div>
</template>

<script>
export default {
    name: 'hello',
    data () {
        return {
            msg: 'Welcome to Your Vue.js App',
            items:[
                {
                    label:'coding',
                    isFinished:false
                },
                {
                    label:'walking',
                    isFinished:true
                }
            ],
            newItem:''
        }
    },
    methods: {
        toggleFinish: function(item) {
            item.isFinished = !item.isFinished;
        },
        addNew:function() {
            console.log(this.newItem);
            this.items.push({
                label:this.newItem,
                isFinished:false
            }),
            this.newItem = ''
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
.finished{
    background-color: #999;
}
</style>
