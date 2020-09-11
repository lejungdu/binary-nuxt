<template>
    <v-form class="searchBar">
      <v-row>
        <v-text-field label="会員番号" v-model="memberNumber" />
        <v-btn type="submit" class="dark" @click.prevent="updateTreeByNumber">検索</v-btn>
      </v-row>
    </v-form>
</template>

<script>
/* eslint-disable */ 
import { mapMutations } from 'vuex'
export default {
    name: "SearchBar",
    props: ['treeOriginal'],
    data: function() {
        return{
            memberNumber: '',
        }
    },
    methods: {
        ...mapMutations(['updateNode']),
        updateTreeByNumber(){
            var currentNode = this.treeOriginal
            var number = Number(this.memberNumber)
            if(currentNode.number === number){
                console.log(currentNode)
                this.updateNode(currentNode.name)
                return
            }
            else{
                this.recursiveFind(currentNode, number)
            }
        },
        recursiveFind(data, number){
            if(data.nodes){
                var n = 0
                while(data.nodes.length > n){
                    if(data.nodes[n].number === number){
                        console.log(data.nodes[n])
                        this.updateNode(data.nodes[n].name)
                        break
                    }
                    this.recursiveFind(data.nodes[n], number)
                    n++
                }
            }
        }
    }
}
</script>

<style scoped>
/* CSS for searchbar */

.searchBar{
  position: absolute;
  top: 3%;
  left: 0%;
}

/* Disable number arrow display on Chrome, Safari, Edge, Opera
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* Disable number arrow display on Firefox */
/* input[type=number] {
  -moz-appearance: textfield;
} */

</style>