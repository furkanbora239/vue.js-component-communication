<template>
    <div class="box">
        <br>
        <h2>PARENT BOX</h2>
        <p> Child-One sey = <strong>{{childOneData}}</strong> // Child-Two sey = <strong>{{childTwoData}}</strong></p>
        <button @click="forChildOne"><strong>&#x2190;</strong></button> <input ref="appİnput" type="text" value="buraya yaz" style="margin-bottom: 3%" @keyup.enter="forBoth"> <button @click="forChildTwo"><strong>&#x2192;</strong></button>
        <table>
            <tr> 
                <th><app-child-one></app-child-one></th> 
                <th><app-child-two/></th>
            </tr>
        </table>
        <br>
    </div>
</template>

<script>
import child1Vue from './child1.vue'
import child2Vue from './child2.vue'
import {eventBus} from '../main'
export default {
    components:{
        appChildOne: child1Vue,
        appChildTwo: child2Vue
    },
    data(){
        return{
            childOneData : "no command",
            childTwoData : "no command"
        }
    },
    methods:{
        forChildTwo(){
            var i = this.$refs.appİnput.value // ref appİnput olan html öğresinin value sunu al demek çok kullanışlı
            eventBus.$emit('forChildTwo', i)
        },
        forChildOne(){
            var i = this.$refs.appİnput.value // ref appİnput olan html öğresinin value sunu al demek çok kullanışlı
            eventBus.$emit('forChildOne', i)
        },
        forBoth(){
            this.forChildTwo()
            this.forChildOne()
        }
    },
    created(){
        eventBus.$on('oneData',(oneData) => {  //tek tırnak kullanmazsan çaloışmıyor '' <-- bunu kullan 
            this.childOneData = oneData
        })
        eventBus.$on('twoData',(twoData)=> {  //tek tırnak kullanmazsan çaloışmıyor '' <-- bunu kullan 
            this.childTwoData = twoData
        })
    }
    
}
</script>

<style scoped>
table{
    width: 100%;
}
input{
    width: 35%;
}

</style>