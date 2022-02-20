<template>
    <div class="box">
        <h3>CHILD-TWO</h3>
        <p> {{gelen_veri}} </p>
        <button @click="forChildOne"><strong>&#x2190;</strong></button> <input ref="appİnput" type="text" value="buraya yaz" @keyup.enter="gonder">
    </div>
</template>

<script>
import {eventBus} from '../main'
export default {
    data(){
        return{
            gelen_veri: "incoming data"
        }
    },
    methods:{
        gonder(event){
            var i = event.target.value
            eventBus.$emit('twoData', i) //tek tırnak kullanmazsan çaloışmıyor '' <-- bunu kullan 
        },
        forChildOne(){
            var i = this.$refs.appİnput.value // ref appİnput olan html öğresinin value sunu al demek çok kullanışlı
            eventBus.$emit('forChildOne', i)
        }
    },
    created(){
        eventBus.$on('forChildTwo', (value) => {
            this.gelen_veri = value
        })
    }
}
</script>

<style>

</style>