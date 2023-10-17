<template>
    <p>Reaction time : {{ score }} ms</p>
    <p class="rank" :style="'color:' + color">{{ rank }}</p>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null,
            color: null,
        }
    },
    mounted() {
        if (this.score < 250) {
            this.rank = 'Ninja fingers';
            this.color = '#33ff00';
        }
        else if (this.score < 400) {
            this.rank = 'Rapid reflexes';
            this.color = '#0faf87';
        }
        else {
            this.rank = 'Snail pace'
            this.color = '#ff0000';
        }
    }
}
</script>

<style>
.rank {
    font-size: 1.4em;
    font-weight: bold;
}

</style>