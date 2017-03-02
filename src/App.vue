<template>
    <div class="container">
        <form>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">

                    <app-name v-model="name"></app-name>

                    <div class="form-group">
                        <label for="email">Email:</label><input type="email" v-model="userData.email" id="email"/>
                    </div>
                    <div class="form-group">
                        <label for="password">Password:</label><input type="password" v-model="userData.password"/>
                    </div>
                    <hr>
                    <app-stored v-model="storedData"></app-stored>
                    <button class="btn" @click.prevent="submitted">Submit!</button>

                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->

                    <!-- Exercise 2 -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->

                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="isSubmitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ userData.Name }}</p>
                        <p>Mail: {{ userData.email }}</p>
                        <p>Password: </p>
                        <p>Store in Database?: {{ storedData }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import Stored from './Stored.vue';
    import Name from './Name.vue';

    export default {
        data () {
            return {
                userData: {
                    name: '',
                    email: '',
                    password: ''
                },
                isSubmitted: false,
                storedData: false
            }
        },
        methods: {
            submitted() {
                this.isSubmitted = true;
            }
        },
        components: {
            appStored: Stored,
            appName: Name
        }

    }
</script>

<style>

</style>
