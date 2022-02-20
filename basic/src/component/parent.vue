<template>
    <div class="container div">
        <h1>EBEVEYN</h1>
        <p>ÇOCUK1'den gelen = '<strong>{{ch1}}</strong>' // ÇOCUK2'den gelen = '<strong>{{ch2}}</strong>'</p>
        <input type="text" v-model="pgdata"> <br>
        <button @click="sendToCh1">send to ÇOCUK1</button>
        <button @click="sendToBoth">ikisinde gönder</button>
        <button @click="sendToCh2">send to ÇOCUK2</button> <br>

        <table class="table">
            <tr>
                <th class="child1"><child-1 :ch1g="c1giden" @child1Data="ch1 = $event" @ch1ToCh2="fromCh1ToCh2($event)"></child-1></th>
                <th class="child2"><child-2 :ch2="c2giden" @child2Data="ch2 = $event" @ch2ToCh1="fromCh2ToCh1($event)"></child-2></th>
            </tr>
        </table>
        
    </div>
</template>

<script>
import child1 from './child1.vue'
import child2 from './child2.vue'
export default {
    components:{
        child1 ,
        child2
    },
    data(){
        return{
            ch1: "çocuk 1 den gelen",
            ch2: "çocuk 2 den gelen",
            pgdata: "giden data",
            c1giden: "gönderilen data",
            c2giden: "gönderilen data"
        }
    },
    methods:{
        sendToCh1(){
            this.c1giden = this.pgdata
        },
        sendToCh2(){
            this.c2giden = this.pgdata
        },
        sendToBoth(){
            this.sendToCh1();
            this.sendToCh2();
        },
        fromCh1ToCh2(data1){
            this.c2giden=data1
        },
        fromCh2ToCh1(data2){
            this.c1giden=data2
        }
    }
}
</script>

<style scoped>
.div{
    background-color: aquamarine;
    text-align: center;
    border-radius: 50px;

}
.child1{
    background-color: bisque;
    text-align: center;
    border-top-left-radius: 35px;
    border-bottom-left-radius: 35px;
}
.child2{
    background-color: blueviolet;
    text-align: center;
    border-top-right-radius: 35px;
    border-bottom-right-radius: 35px;

}
</style>