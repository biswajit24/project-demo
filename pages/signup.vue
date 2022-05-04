<template>
<div class="signup">
    <b-container>
        <div class="form_back">
            <b-form id="form">
                <div class="name_portion">
                    <b-form-group id="input-group-1" label="First Name">
                        <b-form-input id="input_1" type="text" placeholder="" v-model="user.firstname" required></b-form-input>
                    </b-form-group>
                    <b-form-group id="input-group-1" label="Last Name">
                        <b-form-input id="input_1" type="text" placeholder="" v-model="user.lastname" required></b-form-input>
                    </b-form-group>
                </div>
                <b-form-group id="input-group-2" label="Username" label-for="input-2">
                    <b-form-input id="input_1" type="text" placeholder="" v-model="user.username" required></b-form-input>
                </b-form-group>

                <b-form-group id="input-group-2" label="Password" label-for="input-2">
                    <b-form-input id="input_1" type="password" placeholder="" v-model="user.password" required></b-form-input>
                </b-form-group>

                <b-form-group id="input-group-2" label="Confirm Password" label-for="input-2">
                    <b-form-input id="input_1" type="password" placeholder="" v-model="user.confirm_password" required></b-form-input>
                </b-form-group>

                <b-button @click="Formdata" :class="color" class="submit my-3 px-5 py-2">Submit</b-button>
            </b-form>
        </div>
    </b-container>

</div>
</template>

<script>
export default {
    name: 'signup',
    data(){
        return{
            user:{
                firstname:'',
                lastname:'',
                username:'',
                password:'',
                confirm_password:'',
            }
        }
    },
    methods:{
        Formdata(){
            console.log(this.user);
            alert('Thank You');
            localStorage.setItem('firstname',this.user.firstname);
            localStorage.setItem('lastname',this.user.lastname);
            localStorage.setItem('username',this.user.username);
            localStorage.setItem('password',this.user.password);
            localStorage.setItem('confirm_password',this.user.confirm_password);
            let pass = localStorage.getItem('password');
            if(pass){
                this.$router.push('/');
            }
        }
    }
}
</script>

<style scoped>
.signup {
    background: #207398;
    height: 100vh;
    display: flex;
    align-items: center;
}

.form_back {
    width: 50%;
    margin: auto;
    background: rgba(255, 255, 255, 0.25);
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
    backdrop-filter: blur(4px);
    -webkit-backdrop-filter: blur(4px);
    border-radius: 10px;
    border: 1px solid rgba(255, 255, 255, 0.18);
    padding: 38px;
    position: relative;
    z-index: 20;
}

.name_portion {
    display: flex;
    justify-content: space-between;
}

#input_1 {
    background: transparent;
}
.submit{
    text-transform: uppercase;
    letter-spacing: 5px;
}

@media screen and (max-width:1024px) {
    .name_portion{
        flex-direction: column;
    } 
    .form_back{
        width: 75%;
    }
}
@media screen and (max-width:480px) {
    .form_back{
        width: 90%;
    }
}
</style>
