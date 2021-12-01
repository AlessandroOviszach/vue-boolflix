<template>
    <div class="card">
        <img v-if='poster'
        :src="`https://image.tmdb.org/t/p/w342${poster}`" 
        alt=""
        >
        <img v-else src="https://hatrabbits.com/wp-content/uploads/2017/01/random.jpg" :alt="title">

        <ul>
            <li>Titolo: {{ title }} </li>
            <li>Titolo Originale: {{ originaltitle }} </li>
            <li>
                Lingua :
                <img class="flag"
                v-if='isFlag'
                    :src="require(`../assets/${language}.png`)"
                    :alt="language"
                >
                <span v-else>{{ language }}</span>
            </li>
            <li>Voto: {{ vote }} </li>
        </ul>
    </div>
</template>

<script>
export default {
    name : 'Card',
    props : {
        poster : String,
        title : String,
        originaltitle : String,
        language : String,
        vote : Number,
    },

    data() {
        return {
            availableFlags : ['it', 'en'],
        }
    },
    computed: {
        isFlag() {
            return this.availableFlags.includes(this.language);
        }
    },
}
</script>

<style scoped lang='scss'>
.card {
    .flag {
        width: 30px;
    }
}      
</style>