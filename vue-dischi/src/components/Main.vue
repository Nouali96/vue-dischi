<template>
    <main>
        <div class="container pt-5">
            <div class="d-flex flex-wrap">
                <Disc
                    v-for="(discItem, index) in filterDiscs"
                    :key="index"
                    :disc="discItem"
                />
            </div>
        </div>
    </main>
</template>

<script>
import axios from "axios";
import Disc from "./Disc";

export default {
    name: "Main",
    components: {
        Disc,
    },
    props: {
        'selectedGenre': String
    },
    data(){
        return {
            discs:[],
            genres:[],
        };
    },
    computed:{
        filterDiscs() {
            if(this.selectedGenre == ''){
                return this.discs;
            }
            else {
                return this.discs.filter(disc =>{
                    return disc.genre == this.selectedGenre;
                });
            }
        }
    },
    created() {
        axios
            .get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((res)=> {
                this.discs = res.data.response;
                this.discs.forEach(disc => {
                    if(!this.genres.includes(disc.genre)) {
                        this.genres.push(disc.genre);
                    }
                });
                this.$emit('genresReady', this.genres);
            })
            .catch((err) => {
                console.log(err);
            });
    },
}
</script>

<style lang="scss">
    
</style>
