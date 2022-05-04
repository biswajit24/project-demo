<template>
<div class="dashboard">
    <div class="header_back">
        <b-container>
            <b-row>
                <div class="content">
                    <b-navbar toggleable="lg" type="dark">
                        <b-navbar-brand href="#" class="logo">
                            <b-icon icon="list-ul" class="list" @click="navData" :class="listportion" aria-hidden="true"></b-icon>
                        </b-navbar-brand>
                        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
                        <b-collapse id="nav-collapse" is-nav>
                            <b-navbar-nav class="ml-auto">
                                <b-nav-form class="search_all">
                                    <b-form-input class="input_1" placeholder="Search..."></b-form-input>
                                    <b-button class="my-2 my-sm-0 search">
                                        <b-icon icon="search" aria-hidden="true"></b-icon>
                                    </b-button>
                                </b-nav-form>
                                <b-nav-item-dropdown right>
                                    <template #button-content>
                                        <label class="user">User <b-icon icon="chevron-double-down" class="chevron" animation="cylon-vertical" aria-hidden="true"></b-icon></label>
                                    </template>
                                    <b-dropdown-item variant="info" href="#">Profile</b-dropdown-item>
                                    <b-dropdown-item variant="info" href="#" @click="formData">logout</b-dropdown-item>
                                </b-nav-item-dropdown>
                            </b-navbar-nav>
                        </b-collapse>
                    </b-navbar>
                </div>
            </b-row>
            <Cardportion />
            <Barportion />
            <Storage />
        </b-container>
    </div>
    <div class="nav_portion" :class="dashboard">
        <h4>
            <label>Dash</label>
            <b-icon icon="x-circle-fill" class="circle" @click="Datanav" :class="clicking" aria-hidden="true"></b-icon>
        </h4>
        <li>
            <b-row>
                <b-col class="icon_area" :class="icon" cols="5">
                    <b-icon icon="house-fill" aria-hidden="true"></b-icon>
                </b-col>
                <b-col><label class="text" :class="icon_text">home</label></b-col>
            </b-row>
        </li>
        <li>
            <b-row>
                <b-col class="icon_area" :class="icon" cols="5">
                    <b-icon icon="person-fill" aria-hidden="true"></b-icon>
                </b-col>
                <b-col><label class="text" :class="icon_text" @click="aboutPage">about</label></b-col>
            </b-row>
        </li>
        <li>
            <b-row>
                <b-col class="icon_area" :class="icon" cols="5">
                    <b-icon icon="pin-map-fill" aria-hidden="true"></b-icon>
                </b-col>
                <b-col><label class="text" :class="icon_text">map</label></b-col>
            </b-row>
        </li>
        <li>
            <b-row>
                <b-col class="icon_area" :class="icon" cols="5">
                    <b-icon icon="star-half" aria-hidden="true"></b-icon>
                </b-col>
                <b-col><label class="text" :class="icon_text">star</label></b-col>
            </b-row>
        </li>
        <li>
            <b-row>
                <b-col class="icon_area" :class="icon" cols="5">
                    <b-icon icon="bar-chart-fill" aria-hidden="true"></b-icon>
                </b-col>
                <b-col><label class="text" :class="icon_text">bar</label></b-col>
            </b-row>
        </li>
        <li>
            <b-row>
                <b-col class="icon_area" :class="icon" cols="5">
                    <b-icon icon="gear-fill" aria-hidden="true"></b-icon>
                </b-col>
                <b-col><label class="text" :class="icon_text">setting</label></b-col>
            </b-row>
        </li>
    </div>

</div>
</template>

<script>
import Cardportion from '../pages/cardportion.vue'
import Barportion from '../components/Barportion.vue'
import Storage from '../components/Storage.vue'
export default {
    components: {
        Cardportion,
        Barportion,
        Storage,
    },
    name: 'dashboard',
    data() {
        return {
            dashboard: 'nav_portion',
            clicking: 'circle',
            listportion: 'list',
            icon_text: 'text',
            icon: 'icon_area'
        }
    },
    methods: {
        formData() {
            localStorage.clear();
            this.$router.push('/');
        },
        navData() {
            this.dashboard = 'dash';
            this.clicking = 'cross';
            this.listportion = 'list_icon';
            this.icon_text = 'text_change';
        },
        Datanav() {
            this.dashboard = 'nav_portion';
            this.clicking = 'circle';
            this.listportion = 'show';
            this.icon_text = 'text_area';
        },
        aboutPage() {
            this.$router.push('/about');
        }
    }
}
</script>

<style scoped>
.content {
    width: 100%;
}

.header_back {
    width: 100%;
    height: 60px;
    background: #ddd;
}

.input_1 {
    background: transparent;
    border-right: none;
    border-top-right-radius: 0px;
    border-bottom-right-radius: 0px;
    border-color: #000;
}

.logo:hover {
    color: #4f4a51;
}

.search {
    border-left: none !important;
    border-top-left-radius: 0px;
    border-bottom-left-radius: 0px;
    border: 1px solid #000;
    background: #4f4a51;
}

::placeholder,
.user,
.navbar-brand {
    color: #000;
}

.search_all {
    padding: 0px 10px;
}

.user {
    font-size: 18px;
}

.user>.chevron {
    font-size: 16px;
}

.list {
    font-size: 25px;
    color: #000;
}

.list:hover {
    color: #4f4a51;
}

.nav_portion {
    width: 12%;
    height: 100vh;
    background: linear-gradient(160deg, #207398, #4f4a51);
    position: fixed;
    top: 0;
    transition: 0.5s;
}

.nav_portion>li {
    list-style: none;
    text-align: center;
    padding: 20px 0px;
    color: #fff;
    text-transform: uppercase;
    text-align: left;
    cursor: pointer;
    align-items: center;
}

.nav_portion>li:hover {
    background: #ddd;
    color: #207398;
    border-radius: 40px;
}

h4 {
    text-align: center;
    color: #fff;
    text-transform: uppercase;
    margin: 12px 13px;
    display: flex;
    justify-content: space-around;
    align-items: center;
}

.icon_area {
    text-align: right;
    padding-right: 3px;
}

.text {
    cursor: pointer;
    position: fixed;
    visibility: visible;
}

.dash {
    width: 20%;
    transition: 0.5s;
}

.list {
    cursor: pointer;
    position: relative;
    left: -6px;
}

.circle,
.list_icon {
    visibility: hidden;
    cursor: pointer;
}
.cross,
.show {
    visibility: visible;
}

@media screen and (max-width:1200px) {
    .nav_portion {
        transform: translateX(-100%);
    }
    .dash {
        width: 25%;
        transform: translateX(0%);
    }
}

@media screen and (max-width:992px) {

    .navbar-dark .navbar-toggler {
        background: #4f4a51;
    }

    .search_all {
        padding: 15px 10px;
    }

    .navbar-collapse {
        background: #ddd;
    }

    .user {
        padding: 0px 10px;
    }
    .navbar-nav{
        margin-top: 13px;
    }
}
@media screen and (max-width:568px) {
    .dash {
        width: 35%;
        transform: translateX(0%);
    }
    .text, .text_area{
        visibility: hidden;
    }
    .text_change{
        visibility: visible;
    }
    .form-inline{
        flex-flow: nowrap;
        padding: 7px 5px;
    }
}
@media screen and (max-width:480px) {
    .dash {
        width: 40%;
    }
}
@media screen and (max-width:360px) {
    .dash {
        width: 47%;
    }
}
</style>
