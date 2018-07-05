<template>
    <div class="pos">{{ msg }}</div>
</template>

<script>
    export default {
        name: 'Pos',
        data () {
            return {
                msg: 'Hello Pos Demo'
            }
        }
    }
</script>

<style scoped>
.pos {
    overflow: hidden;
    border: 2px solid salmon;
}
</style>
