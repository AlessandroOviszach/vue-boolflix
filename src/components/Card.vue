<template>
    <div class="card">
        <ul>
            <li>Titolo: {{ title }} </li>
            <li>Titolo Originale: {{ originaltitle }} </li>
            <li>
                Lingua :
                <img v-if='availableFlags.includes(language)'
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
        title : String,
        originaltitle : String,
        language : String,
        vote : Number,
    },

    data() {
        return {
            availableFlags : ['it', 'en'],
    }
  }
}
</script>

<style scoped lang='scss'>
.card {
    img {
        width: 30px;
    }
}
</style>