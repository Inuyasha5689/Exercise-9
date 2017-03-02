<template>
    <div>
        <div id="yes" @click="stored(true)" :class="{active: value}">Yes</div>
        <div id="no" @click="stored(false)" :class="{active: !value}">No</div>
    </div>
</template>

<script>
    export default {
        props: ['value'],
        methods: {
            stored (isStored) {
                this.$emit('input', isStored);
            }
        }
    }
</script>

<style scoped="">
    #yes, #no {
        width: 40px;
        height: 20px;
        background-color: lightgray;
        padding: 2px;
        display: inline-block;
        margin: 10px -2px;
        box-sizing: content-box;
        cursor: pointer;
        text-align: center;
    }

    #yes:hover, #yes.active {
        background-color: lightgreen;
    }

    #no:hover, #no.active {
        background-color: lightcoral;
    }
</style>