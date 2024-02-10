<template>
<div>
    <v-checkbox color="blue-lighten-3" :id="myid" :model-value="isDone">
        <template v-slot:label>
          <div></div>{{ theLabel }}
        </template>
    </v-checkbox>
  <!----< input type="checkbox" id="myid" :checked="isDone" :label="theLabel" color="blue-lighten-3" />>-->
  <!--//<label>{{theLabel }}</label> -->
    

</div>
</template>
<script>
import {ref} from "vue";
import uniqueId from "lodash.uniqueid";

const bot=ref(false);
const itemclass=ref("itemcla");
    export default{
        props:{
            label:{required:true,type:String},
            done:{default:false,type:Boolean},
            id:{required:true,type:String},
        },
        data() {
    return {
      mydone:false,
      isDone: this.done,
      theLabel: this.label,
      myid: uniqueId("todo-"),
    };
  },

    };

</script>
<style>
.itemcla{
    color:skyblue
}
</style>