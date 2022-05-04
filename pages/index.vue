<template>
<div class="login">
    <b-container class="bv-example-row">
        <div class="profile">
            <b-icon icon="person" class="user" aria-hidden="true"></b-icon>
        </div>
        <div class="form_portion">
            <h3 class="mb-4">User Login</h3>
            <b-form class="my-4">
                <b-form-group>
                    <b-form-input type="text" placeholder="User Name" v-model="form.username"></b-form-input>
                </b-form-group>
                <b-form-group>
                    <b-form-input type="password" placeholder="Password" v-model="form.password"></b-form-input>
                </b-form-group>
            </b-form>

            <div class="sign_back">
                <label class="sign" @click="Signup">Sign Up</label>
                <label class="forgot">forgot Password?</label>
            </div>
            <b-button class="my-3 px-5 py-2 submit" @click=" formData">login</b-button>
        </div>
    </b-container>

</div>
</template>

<script>
export default {
    name: 'login',

    data() {
        return {
            form: {
                username: '',
                password: ''
            }
        }
    },
    methods: {
        formData() {
            alert('Thank You');
            localStorage.setItem('username', this.form.username);
            localStorage.setItem('password', this.form.password);
            const name = 'biswajit97'
            const pass = 'biswajit2022'
            if (this.form.username == name && this.form.password == pass) {
                this.$router.push('/dashboard')
            }
            this.form = '';
        },
        Signup() {
            this.$router.push('/signup')
        }
    }
}
</script>

<style scoped>
.login {
    text-align: center;
    height: 100vh;
    display: flex;
    align-items: center;
    background: #207398;
    font-family: 'Poppins', sans-serif;
}

.form-control {
    width: 74%;
    margin: auto;
    border: 1px solid #ced4da;
    background: transparent;
}

.form_portion {
    width: 40%;
    height: 100%;
    background: rgba(255, 255, 255, 0.25);
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
    backdrop-filter: blur(4px);
    -webkit-backdrop-filter: blur(4px);
    border-radius: 10px;
    border: 1px solid rgba(255, 255, 255, 0.18);
    margin: auto;
    padding: 20px;
}

.profile {
    width: 120px;
    height: 120px;
    background: linear-gradient(60deg, #207398, #746e78);
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
    border-radius: 50%;
    padding: 10px 0px;
    margin: 0px auto;
    position: relative;
    top: 14px;
    z-index: 2;
    display: flex;
    justify-content: center;
    align-items: center;
}

.user {
    font-size: 35px;
    color: #ced4da;
}

.sign_back {
    display: flex;
    justify-content: space-around;
}

.submit {
    text-transform: uppercase;
    letter-spacing: 5px;
    background: linear-gradient(60deg, #207398, #746e78);
    border: none;
}

h3 {
    color: #746e78;
}

.forgot {
    color: #207398;
    font-style: italic;
    cursor: pointer;
}

.sign {
    color: #746e78;
    cursor: pointer;
}

.sign:hover {
    color: #207398;
}

@media screen and (max-width:1024px) {
    .form_portion {
        width: 60%;
    }
}

@media screen and (max-width:480px) {
    .form_portion {
        width: 80%;
    }

    .profile {
        width: 80px;
        height: 80px;
    }
}

@media screen and (max-width:360px) {
    .form_portion {
        width: 100%;
    }
}
</style>
