<template>
    <div class="container">
        <div class="title">Login</div>
        <FormulateForm @submit='Login'>
            <FormulateInput name="user" label="Usuario" v-bind="formValues.user" validation="required" />
            <FormulateInput type="password" label="Contraseña" v-bind="formValues.user" validation="required" />
            <FormulateInput class="submit" type="submit" label="Ingresar" @click.stop.prevent="Login()" />
        </FormulateForm>
        <p id="login_err" v-if="error">*Ingrese sus datos correctamente</p>
    </div>
</template>

<script>
/* eslint-disable */
import Vue from 'vue'
import VueFormulate from '@braid/vue-formulate'
Vue.use(VueFormulate)

export default {
    name: 'Login',
    data() {
        return {
            formValues: {user:null, password:null},
            error: false
        }
    },
    methods: {
        Login() {
            if(!this.error){ //Implementar la validación a la base de datos uwu
                this.error = true
            }
            else{
                this.$router.push("/index")
            }
        }
    }
}
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Poppins:400,800,900");
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
}

body{
    display: flex;
    background: linear-gradient(135deg, #A9DCE3, #4A6274);
    height: 100vh;
    justify-content: center;
    align-items: center;
}

#login_err{
    color: crimson;
    font-size: 10px;
    font-weight: 400;
}

.container {
    background: white;
    border-radius: 25px;
    width: 100%;
    max-width: 700px;
    padding: 40px 80px;
}

.container label{
    font-size: 15px;
}

.container input {
    margin: 5px 0px 10px 0px;
    width: calc(100% / 2 -20px);
    height: 35px;
    outline: none;
    border: 1px solid #ccc;
    border-radius: 5px;
    transition: all 0.5s ease;
}

.title {
    font-size: 40px;
    font-weight: 600;
    position: relative;
    padding-bottom: 9%;
}

.title::before {
   content: "";
   position: absolute;
   background: linear-gradient(top left, #A9DCE3, #4A6274);
   background-repeat: no-repeat;
   height: 3px;
   width: 35px;
   bottom: 15px;
}

.container input:focus {
    border-color: #a971c4;
}

.container .submit button{
    margin-top: 5%;
    height: 45px;
    width: 100%;
    font-size: 15px;
    border-radius: 15px;
    outline: none;
    border: none;
    text-align: center;
    background: linear-gradient(135deg, #A9DCE3, #4A6274);
    color: white;
    text-transform: uppercase;
    transition: ease 0.5s;
}

.container .submit button:hover{
    cursor: pointer;
    letter-spacing: 3px;
    border-radius: 26px;
}

ul li::before{
    content: "*";
    font-weight: 500;
}

ul li{
    list-style-type: none;
    font-size: 10px;
    position: relative;
    margin: 0px;
    bottom: 10px;
    color: crimson;
}

/*RESPONSIVE PART*/
@media (max-width: 584px) and (max-height: 256px) {
    .container {
        max-width: 100%;
        max-height: 100%;
    }

    .container input{
        width: 100%;
        height: 100%;
    }
}
</style>