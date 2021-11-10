<template>
    <transition name="modal-fade">
        <div class="modal-overlay" @click="$emit('close-modal')">
            <div class="modal" @click.stop>
                <div class="inv-container">
                    <div class="inv-header">
                        <h3>Roblox Inventory</h3>
                    </div>
                    <div class="inv-body">
                        <div class="search-item">
                            <div class="search-item-icon">
                                <img src="https://i.imgur.com/lBx18rK.png" alt="">
                            </div>
                            <input type="search" placeholder="Kangaroo Animal...">
                        </div>
                        <div class="inventory">
                            <InventoryItem v-for="(item, index) in items" :index="index" :item="item" :key="index" @click.native="toggleClick(item)"/>
                        </div>
                    </div>
                </div>
                <div class="modal-content">
                    <div class="inner-modal">
                        <div class="inner-modal-header">
                            <h3>Selected Items</h3>
                        </div>
                        <div class="selected-items">
                            <div class="item" v-for="index in 8" :key="index">
                                <div class="icon">
                                    <img src="https://i.imgur.com/1EnC66x.png" alt="Kangaroo">
                                </div>
                                <div class="details">
                                    <div class="item-title">Kangaroo Animal</div>
                                    <div class="item-number">4 423 12$</div>
                                </div>
                                <div class="buttons">
                                    <img src="https://i.imgur.com/w1JyShZ.png" alt="">
                                    <img src="https://i.imgur.com/CFYYqMf.png" alt="">
                                    <img src="https://i.imgur.com/pYmbcVr.png" alt="">
                                </div>
                            </div>
                        </div>

                        <div class="modal-footer">
                            <div class="value">
                                Value = $500
                            </div>
                            <div class="btn-create">Create Game</div>
                            <div class="select-coin">
                                <span>Select Your Coin</span>
                                <img src="https://i.imgur.com/zHWvSNt.png" class="red" alt="Red Coin" @click="toggleCoin">
                                <img src="https://i.imgur.com/C08dmIT.png" class="blue" alt="Blue Coin" @click="toggleCoin">
                            </div>
                        </div>
                    </div>
                    <div class="close" @click="$emit('close-modal')">
                        <img class="close-img" src="~/assets/images/close-icon.svg" alt="" />
                    </div>
                </div>
            </div>
        </div>
    </transition>
</template>

<script>
export default {
    data() {
        return {
            items: [
               { isActive: false },
               { isActive: false },
               { isActive: false },
               { isActive: false },
               { isActive: false },
               { isActive: false },
               { isActive: false },
               { isActive: false },
               { isActive: false },
               { isActive: false },
               { isActive: false },
               { isActive: false },
               { isActive: false },
               { isActive: false },
               { isActive: false },
               { isActive: false },
            ]
        }
    },
    methods: {
        toggleCoin: function(event) {
            if (event.target.classList.contains("active")) {
                event.target.classList.remove("active");
                return;
            }
            event.target.classList.add("active");
        },
        toggleClick: function(item) {
            console.log(item)
            item.isActive = !item.isActive
        },
    }
}
</script>

<style scoped>
.search-item {
    position: absolute;
    top: 80px;
    left: 80px;
}

input[type="search"] {
    width: 227px;
    height: 32px;
    background: #23212D;
    border: 1px solid #1E1E29;
    box-sizing: border-box;
    border-radius: 10px;
    font-family: Roboto;
    font-style: normal;
    font-weight: normal;
    font-size: 17px;
    line-height: 20px;
    letter-spacing: 0.085em;
    color: #FFFFFF;
    padding: 3px;
    padding-left: 28px;
    position: relative;
}

.search-item-icon {
    position: absolute;
    top: 50%;
    left: 5px;
    height: 17px;
    width: 17px;
    z-index: 500;
    transform: translateY(-50%);
}

.search-item-icon > img {
    height: 17px;
    width: 17px;
}

input[type="search"]::placeholder {
    font-family: Roboto;
    font-style: normal;
    font-weight: normal;
    font-size: 17px;
    line-height: 20px;
    letter-spacing: 0.085em;
    color: #FFFFFF;
    opacity: 0.8;
}

.inv-body {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 100%;
}

.inv-body .inventory {
    display: flex;
    flex-direction: row;
    align-items: center;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    padding: 40px;
    padding-top: 20px;
    overflow-y: auto;
    max-height: 552px;
}

.inventory::-webkit-scrollbar-track {
    border-radius: 10px;
    background: #23212D;
    border: 1px solid rgba(152, 95, 240, 0.1);
}

.inventory::-webkit-scrollbar {
  width: 5px;
  background-color: transparent;
}

.inventory::-webkit-scrollbar-thumb {
  border-radius: 10px;
  background-color: #AB5A5E;
}

.inv-header {
    width: 100%;
    display: flex;
    justify-content: center;
}

.inv-header > h3 {
    font-family: Varela Round;
    font-style: normal;
    font-weight: normal;
    font-size: 30px;
    line-height: 36px;
    display: flex;
    align-items: center;
    text-align: center;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    color: #FFFFFF;
    margin-bottom: 70px;
}

.select-coin {
    width: 226px;
    height: 43px;
    background: #1E1C24;
    border-radius: 15px;
    display: flex;
    gap: 13px;
    align-items: center;
    justify-content: center;
}

.select-coin > img {
    width: 29px;
    height: 28px;
}

.select-coin > img.red.active {
    filter: drop-shadow(0px 4px 4px #A41212);
}

.select-coin > img.blue.active {
    filter: drop-shadow(0px 4px 4px #2E7EA2);
}

.select-coin > span {
    font-family: Montserrat;
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 15px;
    display: flex;
    align-items: center;
    color: #828282;
    text-transform: uppercase;
}

.modal-footer {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    flex-direction: column;
    flex-grow: 1;
    margin-bottom: 20px;
}
.btn-create {
    font-family: Montserrat;
    font-style: normal;
    font-weight: bold;
    font-size: 25px;
    line-height: 30px;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: #FFFFFF;
    cursor: pointer;
    background: #8C3537;
    border: 1px solid #A40D0D;
    box-sizing: border-box;
    border-radius: 10px;
    width: 219px;
    height: 42px;
    text-transform: uppercase;
    margin: 15px 0;
}

.value {
    width: 217px;
    height: 31px;
    background: #23212D;
    border: 1px solid rgba(147, 147, 147, 0.25);
    box-sizing: border-box;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: Montserrat;
    font-style: normal;
    font-weight: bold;
    font-size: 15px;
    line-height: 18px;
    text-align: center;
    letter-spacing: 0.055em;
    color: #FFFFFF;
}

.buttons {
    display: flex;
    gap: 6px;
    cursor: pointer;
}

.buttons > img {
    height: 14px;
    width: 15px;
}

.selected-items {
    width: 100%;
    display: flex;
    flex-direction: column;
    max-height: 500px;
    overflow-y: auto;
}

.selected-items::-webkit-scrollbar {
    display: none;
}

.item {
    background: #1B1B25;
    border-radius: 5px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 8px;
}

.item:nth-child(even) {
    background: #23212D;
}

.item-title {
    font-family: Roboto;
    font-style: normal;
    font-weight: bold;
    font-size: 10px;
    line-height: 12px;
    color: #FFFFFF;
}

.item-number {
    font-family: Roboto;
    font-style: normal;
    font-weight: bold;
    font-size: 15px;
    line-height: 18px;
    color: #FFFFFF;
}

.item > .icon {
    width: 46px;
    height: 46px;
    background: linear-gradient(180deg, #EB357D 60%, rgba(0, 0, 0, 0) 83%);
    /* background: linear-gradient(180deg, #EB357D 69.27%, rgba(0, 0, 0, 0) 100%); */
    border-radius: 15px;

    /* border: 1px solid transparent;
    border-image-source: linear-gradient(180deg, #EB357D 69.27%, rgba(0, 0, 0, 0) 100%);
    border-image-slice: 2; */

   /*  background-image: url('https://i.imgur.com/1EnC66x.png');
    background-size: contain;
    background-position: center; */
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
}

.item > .icon::after {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    height: 44px;
    width: 44px;
    background: #272530;
    border-radius: 15px;
}

.item > .icon > img {
    width: 35px;
    height: auto;
    position: relative;
    z-index: 100;
}

.inv-container {
    height: 777px;
    flex-grow: 1;
    position: relative;
    z-index: 200;
}

.inner-modal {
    position: absolute;
    display: flex;
    align-items: flex-start;
    flex-direction: column;
    height: 100%;
    width: 100%;
    gap: 12px;
    z-index: 100;
    padding-bottom: 20px;
}

.inner-modal-header {
    padding-left: 10px;
}

.inner-modal-header h3 {
    font-family: Montserrat;
    font-style: normal;
    font-weight: bold;
    font-size: 20px;
    line-height: 24px;
    color: #fff;
}

.modal-content {
    width: 250px;
    min-width: 250px;
    height: 777px;
    background: #23212D;
    box-sizing: border-box;
    border-radius: 10px;
    position: relative;
    z-index: initial;
}

.modal-overlay {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    justify-content: center;
    background-color: rgba(23, 23, 33, 0.5);
    z-index: 45;
}

.modal {
    text-align: center;
    background-color: #171721;
    width: 1125px;
    height: 776px;
    margin-top: 75px;
    z-index: 50;
    position: relative;
    border-radius: 10px;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: row;
}

.modal::after {
    content: '';
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 51;
    background-color: #171721;
    background-image: url('https://i.imgur.com/Y7Uf42E.png');
    background-position: center;
    background-size: cover;
    opacity: 5%;
}

.close {
    position: absolute;
    top: 12px;
    right: 12px;
    cursor: pointer;
    z-index: 100;
}

.close-img {
    width: 25px;
}

.check {
    width: 150px;
}

.modal-fade-enter,
.modal-fade-leave-to {
    opacity: 0;
}

.modal-fade-enter-active,
.modal-fade-leave-active {
    transition: opacity 0.5s ease;
}
</style>