<template>
  <div class="hello">
    <h1> Simple TO-DO </h1>
    
    <input type="text" v-model="addItem"> <button @click="Add(addItem)"> Add Item</button>



    <ul >
      <div v-for="item in list" v-bind:key="item.id">

        {{item}}
        <button @click="Remove(item.id)"> X </button>
      </div>
    </ul>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class ToDo extends Vue {
  list: string[] = [];
  addItem: string= "";
  Add(item: string){
    this.list.push(item);
    this.addItem = "";
    }

  Remove(index: number){
    this.list.splice(index,1);
  }


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  text-align: center;
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
</style>
