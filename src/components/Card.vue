<template>
    <div class="card">
        <ul>
            <li>Titolo: {{ title }} </li>
            <li>Titolo Originale: {{ originaltitle }} </li>
            <li>Lingua: {{ language }} </li>
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

    }
}
</script>

<style scoped lang='scss'>

</style>