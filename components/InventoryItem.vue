<template>
    <div class="item-container">
        <div class="inv-item" :class="[isGreen(index) ? 'green' : 'red', {active: item.isActive}]">
            <div class="inv-item-content">
                <div class="buttons">
                    <img src="https://i.imgur.com/w1JyShZ.png" alt="">
                    <img src="https://i.imgur.com/CFYYqMf.png" alt="">
                    <img src="https://i.imgur.com/pYmbcVr.png" alt="">
                </div>
                <img src="https://i.imgur.com/1EnC66x.png" alt="Kangaroo">
                <hr>
                <h3>Kangaroo Animal</h3>
                <div class="inv-item-number">4 423 12$</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['index', 'item'],
    methods: {
        isGreen: function(index) {
            return index % 2 == 0
        }
    }
}
</script>

<style scoped>
.buttons {
    display: flex;
    gap: 6px;
    cursor: pointer;
}

.buttons > img {
    height: 14px;
    width: 15px;
}
.inv-item-content {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    position: relative;
    width: 159px;
    height: 184px;
    z-index: 150;
}

.inv-item {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    width: 159px;
    height: 184px;
    border-radius: 15px;
    position: relative;
    z-index: 50;
    cursor: pointer;
    transition: all 0.25s ease-in-out;
}

.inv-item.green {
    background: linear-gradient(180deg, #8EC643 69.27%, rgba(0, 0, 0, 0) 92%);
}

.inv-item.red {
    background: linear-gradient(180deg, #EB357D 69.27%, rgba(0, 0, 0, 0) 92%);
}

.inv-item:hover {
    transform: scale(1.08);
    /* background: linear-gradient(180deg, #35b1eb 69.27%, rgba(0, 0, 0, 0) 92%); */
}

.inv-item.green.active {
    filter: drop-shadow(0 0 0.35rem #8EC643);
}

.inv-item.red.active {
    filter: drop-shadow(0 0 0.35rem #EB357D);
}

.inv-item::after {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 156px;
    height: 182px;
    background: #272530;
    border-radius: 15px;
}

.inv-item-content > .buttons {
    margin-bottom: 5px;
}

.inv-item-content > hr {
    width: 99px;
}

.green .inv-item-content hr {
    border: 1px solid #8EC643;
}

.red .inv-item-content hr {
    border: 1px solid #EB357D;
}

.inv-item-number {
    font-family: Roboto;
    font-style: normal;
    font-weight: bold;
    font-size: 15px;
    line-height: 18px;
    color: #FFFFFF;
}

.inv-item-content > h3 {
    font-family: Roboto;
    font-style: normal;
    font-weight: bold;
    font-size: 10px;
    line-height: 12px;
    color: #FFFFFF;
    margin: 0;
}

.inv-item-content > img {
    width: auto;
    height: 92px;
}
</style>