<template>
    <div>
        <h1>form validation demonstration</h1>
        <p v-if="error.length">
            <b>Please correct the following errors</b>
            <ul>
                <li>
                    <h4 v-for="err in error" :key="err.id">
                        {{err}}
                    </h4>
                </li>
            </ul>
        </p>

        <form v-on:submit="login">
            <input type="text" name="" id="" placeholder="Name" v-bind="name"> <br><br>
            <input type="password" name="" id="" placeholder="Password" v-bind="password"><br><br>
            <button type="submit">submit </button>
        </form>

    </div>
</template>
<script>
export default {

    name:'formValidation',

    data(){
        return {
            error:[],
            name:null,
            password:null
        }
    },

    methods:{
        login(e){
            
            if(this.name && this.password){
                console.warn('no errors')
            }
            if( this.name ){
                this.error.push("plz enter the name");
            }
            if( this.password  ){
                this.error.push("plz enter the password");
            }
            console.warn('hello' ,this.error)
            e.preventDefault()
        }
    }

}
</script>