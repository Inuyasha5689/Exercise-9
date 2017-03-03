<template>
    <div class="container">
        <form>
            <div class="row" v-if="!isSubmitted">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">

                    <app-name v-model="userData.fullName"></app-name>

                    <div class="form-group">
                        <label for="email">Email:</label><input class="form-control" type="email" v-model="userData.email" id="email"/>
                    </div>
                    <div class="form-group">
                        <label for="password">Password:</label><input class="form-control" type="password" v-model="userData.password"/>
                    </div>
                    <hr>
                    <div class="form-group">
                        <label><input type="radio" value="Yes" v-model="storedData"/>Yes</label>
                    
                    
                        <label><input type="radio" value="No" v-model="storedData"/>No</label>
                    </div>
                    <button class="btn btn-primary" @click.prevent="submitted">Submit!</button>

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
                        <p>Full Name: {{ userData.fullName }}</p>
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
    import Name from './Name.vue';

    export default {
        data () {
            return {
                userData: {
                    fullName: 'Drake Scott',
                    email: '',
                    password: ''
                },
                isSubmitted: false,
                storedData: 'Yes'
            }
        },
        methods: {
            submitted() {
                this.isSubmitted = true;
            }
        },
        components: {
            appName: Name
        }

    }
</script>

<style>

</style>
