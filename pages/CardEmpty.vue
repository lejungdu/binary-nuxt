<template>
<!-- eslint-disable -->
    <v-card class="node">
        <img :src="require(`~/static/diamond_gfc.svg`)">
        <div class="topLevel">
            <div class="upgrade">昇格まで A 2人 B 4人</div>
            <div class="nickname">N.E.</div>
            <div class="memberID">1234567</div>
        </div>
        <div class="midLevel">
            <div class="leftSide">
                <div class="category">A</div>
                <div class="people">101人</div>
                <div class="amount">総仕入額</div>
                <div class="totalAmount">8,000</div>
            </div>
            <div class="rightSide">
                <div class="category">B</div>
                <div class="people">65人</div>
                <div class="amount">総仕入額</div>
                <div class="totalAmount">10,000,000</div>
            </div>
        </div>
        <div class="bottomLevel">
            <div class="snsSale"><span>SNS小売り</span><span> 80,000,000</span></div>
            <div class="reward"><span>報酬</span><span> 8,000</span></div>
            <div class="dividend"><span>分配金</span><span> 8,000</span></div>
        </div>
    </v-card>
</template>

<style scoped>

.node {
    padding: 0 16px;
    width: 225px;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    padding-top: 20px;
}

img {
    width: 100px;
    position: absolute;
    left: 50%;
    top: 0%;
    transform: translate(-50%, -50%);
}

/* topLevel layout */

.nickname {
    font-weight: bold;
    font-size: 24px;
    text-align: center;
}

.upgrade, .memberID {
    font-size: 12px;
    text-align: center;
    color: rgba(0,0,0,0.48);
}

/* midLevel layout */

.midLevel {
    display: flex;
    justify-content: space-between;
}

.leftSide {
    padding: 10px 0px;
    text-align: left;
    width: 50%;
    border-top: 2px solid #B5B5B5;
    border-bottom: 2px solid #B5B5B5;
    border-right: 2px solid #B5B5B5;
}
.rightSide {
    padding: 10px 0px;
    text-align: right;
    width: 50%;
    border-top: 2px solid #B5B5B5;
    border-bottom: 2px solid #B5B5B5;
}

.category, .amount {
    font-size: 12px;
}

.people, .totalAmount {
    color: blue;
    font-size: 16px;
    font-style: italic;
    font-weight: bold;
}

/* bottomLevel layout */

.bottomLevel span {
    display: inline-block;
    height: 30px;
    line-height: 30px;
}

.bottomLevel span:nth-child(1){
    font-size: 12px;
}

.bottomLevel span:nth-child(2){
    color: blue;
    font-size: 16px;
    font-style: italic;
    font-weight: bold;
}

.snsSale, .reward, .dividend{
    display: flex;
    justify-content: space-between;
}

</style>
