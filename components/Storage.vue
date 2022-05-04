<template>
<div class="storage">
    <b-row class="direction">
        <b-col>
            <b-row>
                <b-col>
                    <div class="icon_portion">
                        <b-icon icon="house-fill" class="icon" aria-hidden="true"></b-icon>
                        <span>user panel</span>
                    </div>
                    <div class="icon_portion_2">
                        <b-icon icon="arrow-down" class="icon" aria-hidden="true"></b-icon>
                        <span>updates</span>
                    </div>
                </b-col>
                <b-col>
                    <div class="icon_portion_2">
                        <b-icon icon=" cloud-upload" class="icon" aria-hidden="true"></b-icon>
                        <span>cloud storage</span>
                    </div>
                    <div class="icon_portion">
                        <b-icon icon="eye" class="icon" aria-hidden="true"></b-icon>
                        <span>web visits</span>
                    </div>
                </b-col>
            </b-row>
        </b-col>
        <b-col>
            <div class="status_portion">
                <b-row>
                    <b-col class="distance"><label class="text_status">Current status</label></b-col>
                    <b-col class="distance">
                        <label>
                            <b-icon icon="bar-chart-fill" class="bar" aria-hidden="true"></b-icon>
                        </label>
                    </b-col>
                    <b-col class="distance">
                        <label>
                            <b-icon icon="three-dots" class="dot_three" aria-hidden="true"></b-icon>
                        </label>
                    </b-col>
                </b-row>

            </div>
        </b-col>
        <b-col>
            <div class="storage_portion">
                <b-row>
                    <b-col class="distance"><label class="text_cloud">Cloud storage</label></b-col>
                    <div class="circle distance">
                        <b-icon icon="cloud-upload" class="cloud_icon" animation="cylon-vertical" aria-hidden="true"></b-icon>
                    </div>
                    <b-col class="distance"><label>
                            <b-icon icon="three-dots" class="dot" aria-hidden="true"></b-icon>
                        </label></b-col>
                </b-row>
            </div>
        </b-col>
    </b-row>

</div>
</template>

<script>
export default {
    name: 'Storage',
}
</script>

<style scoped>
.user {
    color: #000;
    padding: 0px 5px;
}

.icon_portion {
    width: 100%;
    height: 70px;
    background: #207398;
    margin-bottom: 15px;
    border-radius: 10px;
    display: grid;
    place-items: center;
}

.distance {
    margin: 0px 12px;
}

.icon_portion_2 {
    width: 100%;
    height: 70px;
    background: linear-gradient(160deg, #207398, #4f4a51);
    margin-bottom: 15px;
    border-radius: 10px;
    display: grid;
    place-items: center;
}

.status_portion {
    width: 100%;
    height: 91%;
    background: #ddd;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.storage_portion {
    width: 100%;
    height: 91%;
    background: #207398;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.circle {
    width: 70px;
    height: 70px;
    border-radius: 50%;
    background: #ddd;
    display: grid;
    place-items: center;
}

.cloud_icon {
    font-size: 30px;
    color: #207398;
}

.text_cloud,
.dot {
    position: relative;
    top: -25px;
    color: #ddd;
    text-transform: capitalize;
}

.text_status,
.dot_three {
    position: relative;
    top: -25px;
    text-transform: capitalize;
    color: #207398;
}

.bar {
    font-size: 55px;
    color: #207398;
}

.icon {
    color: #ddd;
}

span {
    text-transform: capitalize;
    color: #ddd;
}

@media screen and (max-width:992px) {
    span {
        font-size: 12px;
    }
    .distance{
        margin: 0px;
    }
    .status_portion, .storage_portion{
        padding: 0px 10px;
    }
}

@media screen and (max-width:768px) {
    .direction{
        flex-direction: column;
    }
    .status_portion, .storage_portion{
        padding: 35px 0px;
    }
    span {
        font-size: 16px;
    }
    .distance{
        margin: 0px 25px;
    }
}

@media screen and (max-width:360px){
    .distance{
        margin: 0px 21px;
        padding: 0px 10px;
    }
}
</style>
