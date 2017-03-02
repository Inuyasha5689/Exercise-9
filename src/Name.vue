<template>
    <div class="form-group">
        <label for="firstName">First Name:</label><input type="text" @clicked="firstName(firstName)" id="firstName" v-model="firstName">
        <label for="lastName">Last Name:</label><input type="text" @clicked="lastName(lastName)" id="lastName" v-model="lastName"/>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                lastName: '',
                firstName: ''
            }
        },
        methods: {
            firstName (name) {
                this.$emit('input', name);
            },
            lastName (name) {
                this.$emit('input', name);
            }
        }
    }
</script>

<style>

</style>