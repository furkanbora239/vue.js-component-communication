<template>
    <div class="box">
        <h3>CHILD-ONE</h3>
        <p> {{gelen_veri}} </p>
        <input ref="appİnput" type="text" value="buraya yaz" @keyup.enter="gonder"> <button @click="forChildTwo"><strong>&#x2192;</strong></button>
    </div>
</template>

<script>
import { eventBus } from "../main.js"
export default {
    data(){
        return{
            gelen_veri: "incoming data"
        }
    },
    methods:{
        gonder(event){
            var i = event.target.value
            eventBus.$emit('oneData', i) //tek tırnak kullanmazsan çaloışmıyor '' <-- bunu kullan 
        },
        forChildTwo(){
            var i = this.$refs.appİnput.value // ref appİnput olan html öğresinin value sunu al demek çok kullanışlı
            eventBus.$emit('forChildTwo', i)
        }
    },
    created(){
        eventBus.$on('forChildOne', (value) => {
            this.gelen_veri = value
        })
    }
    
}
</script>

<style scoped>

</style>