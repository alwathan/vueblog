<template>
    <h1>Hello World!</h1>
     <h4>Project Vue Pertama Saya</h4>
    <h4>Nama Saya {{ nama }}</h4>
    <h4>Umur Saya {{ umur }} tahun</h4>
    <hr>
    <h4>{{ bilangan }}</h4>
    <button v-on:click="next">Next</button>
    <hr>
    <h4>{{ messages }}</h4>
    <input v-model="messages" />
    <hr>
    <h4 v-if="ganjil">Ganjil</h4>
    <h4 v-if="genap">Genap</h4>
    <button v-on:click="randomNumber">Generate</button>
    <hr>
    <table border=1>
        <tr v-for="hari in namaHari" v-bind:key="hari">
            <td>{{ hari }}</td>
        </tr>
    </table>
</template>

<script>
export default{
    data(){
        return{
            nama : "Ach jazuli",
            umur    : 35,
            bilangan : 1,
            messages : '',
            ganjil : false,
            genap : false,
            namaHari : ["Senin", "Selasa", "Rabu", "Kamis",
                        "Jumat", "Sabtu", "Minggu"
                        ]
        }
    },
    mounted(){
        this.umur = this.umur + 5;
        this.randomNumber();
    },
    methods:{
        next(){
            this.bilangan += 1;
            this.showHide();
        },
        randomNumber(){
            this.bilangan = Math.floor(Math.random()*100);
            this.showHide();
        },
        showHide(){
            if(this.bilangan%2==0){
                this.genap = true;
                this.ganjil = false;
            }else{
                this.genap = false;
                this.ganjil = true; 
            }
        }
    } 
}
</script>

<style scoped>

</style>