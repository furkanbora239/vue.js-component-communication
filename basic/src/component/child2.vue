<template>
    <div>
        <h1>ÇOCUK 2</h1>
        <p>{{gdata2}}</p>
        <input type="text" v-model="sdata2"> <br>
        <button @click="sendToParend">send to EBEVEYİN</button>
        <button @click="sendToCh1">send to ÇOCUK1</button> <br>
    </div>
</template>

<script>
export default {
    data(){
        return{
            gdata2: "gelen data",
            sdata2: "giden"
        }
    },
    props:[
        "ch2"
    ],
    watch:{
        ch2(){
            this.gdata2 = this.ch2
        }
    },
    methods:{
        sendToParend(){
            this.$emit("child2Data", this.sdata2)
        },
        sendToCh1(){
            this.$emit("ch2ToCh1", this.sdata2)
        }
    }
}
</script>

<style>

</style>