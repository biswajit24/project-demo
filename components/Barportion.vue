<template>
<div class="barportion">
    <b-row class="direct">
        <b-col>
            <div class="weather_portion">
                <div class="weather">
                    <b-row class="align-items-center">
                        <b-col class="px-5"><label class=" text-capitalize">Current <br> weather</label> </b-col>
                        <b-col class="px-5">
                            <b-icon icon="clouds-fill" class="cloud_fill" aria-hidden="true"></b-icon>
                        </b-col>
                        <b-col class="px-5"><span>21</span></b-col>
                    </b-row>
                </div>
                <div class="health">
                    <b-row class="align-items-center">
                        <b-col class="px-5"><label class=" text-capitalize"> Health <br> care</label></b-col>
                        <b-col class="px-5">
                            <b-icon icon="heart-fill" class="heart" animation="throb" aria-hidden="true"></b-icon>
                        </b-col>
                        <b-col class="px-5"><span>68</span></b-col>
                    </b-row>
                </div>
            </div>
        </b-col>
        <b-col>
            <div class="bar mt-3">
                <b-row class="direct">
                    <b-col class="bar_text mt-3"><label class="memory">Current memory load</label></b-col>
                    <div class="circle-wrap">
                        <div class="circle">
                            <div class="mask half">
                                <div class="fill">
                                </div>
                            </div>
                            <div class="mask full">
                                <div class="fill">
                                </div>
                            </div>
                            <div class="inside-circle"> 75% </div>
                        </div>
                    </div>
                    <b-col class="bar_text mt-3">
                        <label class="dots_portion">
                            <b-icon icon="three-dots" aria-hidden="true"></b-icon>
                        </label>
                    </b-col>
                </b-row>
            </div>
        </b-col>

    </b-row>

</div>
</template>

<script>
export default {
    name: 'Barportion',
}
</script>

<style scoped>
.bar {
    width: 100%;
    background: #ddd;
    height: 88%;
    border-radius: 10px;
}

.weather,
.health {
    width: 100%;
    height: 125px;
    background: #ddd;
    margin: 17px 0px;
    border-radius: 10px;
    display: grid;
    place-items: center;
    align-items: center;
}

.bar_text {
    display: flex;
    justify-content: center;
}

.cloud_fill {
    color: #7e9fb2;
    font-size: 35px;
}

.heart {
    color: #fe7088;
    font-size: 35px;
}

span {
    font-size: 25px;
    color: #207398;
}

.memory {
    text-transform: capitalize;
}

.circle-wrap {
    margin: 70px auto;
    width: 150px;
    height: 150px;
    background: #fefcff;
    border-radius: 50%;
    border: 1px solid #cdcbd0;
}

.circle-wrap .circle .mask,
.circle-wrap .circle .fill {
    width: 150px;
    height: 150px;
    position: absolute;
    border-radius: 50%;
}

.mask .fill {
    clip: rect(0px, 75px, 150px, 0px);
    background-color: #207398;
}

.circle-wrap .circle .mask {
    clip: rect(0px, 150px, 150px, 75px);
}

.mask.full,
.circle .fill {
    animation: fill ease-in-out 3s;
    transform: rotate(135deg);
}

@keyframes fill {
    0% {
        transform: rotate(0deg);
    }

    100% {
        transform: rotate(135deg);
    }
}

.circle-wrap .inside-circle {
    width: 122px;
    height: 122px;
    border-radius: 50%;
    background: #d2eaf1;
    line-height: 120px;
    text-align: center;
    margin-top: 14px;
    margin-left: 14px;
    color: #207398;
    position: absolute;
    z-index: 100;
    font-weight: 700;
    font-size: 2em;
}

@media screen and (max-width:1024px) {
    .bar {
        padding: 0px 10px;
    }
}

@media screen and (max-width:768px) {
    .direct {
        display: grid;
        place-items: center;
    }

    .circle-wrap {
        margin: 22px auto;
    }

    .bar_text>.dots_portion {
        position: relative;
        top: -15px;
    }

    .bar {
        margin-bottom: 15px;
    }
}

@media screen and (max-width:568px) {
    .direct {
        flex-direction: column;
    }

    .bar {
        margin-bottom: 15px;
    }

}
</style>
