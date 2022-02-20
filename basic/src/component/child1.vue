<template>
    <div>
        <h1>ÇOCUK 1</h1>
        <p>{{gdata1}}</p>
        <input type="text" v-model="sdata1"> <br>
        <button @click="sendToParend">send to EBEVEYİN</button>
        <button @click="sendToCh2">send to ÇOCUK2</button> <br>
    </div>
</template>

<script>
export default {
    data(){
        return{
            gdata1: "gelen data",
            sdata1: "giden"
        }
    },
    props:{
        ch1g:{}
    },
    watch:{
        ch1g(){
            this.gdata1 = this.ch1g
        }
    },
    methods:{
        sendToParend(){
            this.$emit("child1Data",this.sdata1)
        },
        sendToCh2(){
            this.$emit("ch1ToCh2",this.sdata1)
        }
    }
    
}
</script>

<style>

</style>