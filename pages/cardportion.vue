<template>
<div class="cardportion">
    <b-row class="mt-2 direct">
        <b-col>
            <b-card img-top tag="article" class="mb-2">
                <div class="box mb-3">
                    <label>Current month revenue</label>
                    <label>
                        <b-icon icon="bar-chart-line-fill" aria-hidden="true"></b-icon>
                    </label>
                </div>
                <b-card-text>
                    <h2>$ 12,456</h2>
                    <p class="text_1">
                        <b-icon icon="plus-circle-dotted" aria-hidden="true"></b-icon> 5% higher than last month
                    </p>
                </b-card-text>
            </b-card>
        </b-col>
        <b-col>
            <b-card img-top tag="article" class="mb-2">
                <div class="box mb-3">
                    <label>Today's visits</label>
                    <label>
                        <b-icon icon="eye" aria-hidden="true"></b-icon>
                    </label>
                </div>
                <b-card-text>
                    <h2>1,456,023</h2>
                    <p class="text_1">
                        <b-icon icon="plus-circle-dotted" aria-hidden="true"></b-icon> 9% higher than last month
                    </p>
                </b-card-text>
            </b-card>
        </b-col>
        <b-col>
            <b-card img-top tag="article" class="mb-2">
                <div class="box mb-3">
                    <label>Today's feedbacks</label>
                    <label>
                        <b-icon icon="arrow-left-right" aria-hidden="true"></b-icon>
                    </label>
                </div>
                <b-card-text>
                    <h2>2,300</h2>
                    <p class="text_1">
                        <b-icon icon="plus-circle-dotted" aria-hidden="true"></b-icon> 3% lower than last month
                    </p>
                </b-card-text>
            </b-card>
        </b-col>
    </b-row>

</div>
</template>

<script>
export default {
    name: 'Cardportion',
}
</script>

<style scoped>
.box {
    width: 100%;
    height: 50px;
    background: linear-gradient(160deg, #207398, #4f4a51);
    display: flex;
    align-items: center;
    justify-content: space-around;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
}

.box>label {
    color: #fff;
    text-transform: capitalize;
}

h2,
.text_1 {
    text-align: center;
    margin-bottom: 30px;
}

.card-body {
    padding: 0px;
}

.card {
    border-radius: 10px;
}

@media screen and (max-width:992px) {
    .box {
        flex-direction: column;
        justify-content: center;
        padding: 32px 0px;
    }

    .box>label:first-child {
        position: relative;
        top: 5px;
    }

    .text_1 {
        display: grid;
        place-items: center;
    }
}

@media screen and (max-width:768px) {
    .direct {
        flex-direction: column;
    }

}
</style>
