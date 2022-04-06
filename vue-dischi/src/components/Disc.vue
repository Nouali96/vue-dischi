<template>
    <div class="disc p-3 text-center">
        <div class="p-3">
            <img class="img-fluid mb-3" :src="disc.poster" :alt="disc.name" />
            <p class="title text-uppercase fw-bold">{{disc.title}}</p>
            <p class="author lead mb-8 ">{{disc.author}}</p>
            <p class="year">{{disc.year}}</p>
        </div>

    </div>
</template>

<script>
export default {
    name:"Disc",
    props: {
        disc: Object,
    },
}
</script>

<style lang="scss" scoped>
    .disc {
        flex-basis: calc(100% / 5);    
    }
    .disc>div {
            background-color: #2e3a46;
            height: 100%;
    }
    .author, .year{
        color: grey;
    }
    .title{
        color: white;
    }
</style>