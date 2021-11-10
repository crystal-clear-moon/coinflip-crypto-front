<template>
    <div class="main-page">
        <div class="header">
            <div class="left"><h1>Active Games</h1></div>
            <div class="right">
                <div class="header-stats">
                    <div class="stat">
                        <div class="number"><span>$</span>5203<span>.</span>23</div>
                        <span>Total Amount</span>
                    </div>
                    <div class="stat">
                        <div class="number">34</div>
                        <span>Games</span>
                    </div>
                    <div class="stat">
                        <div class="number">1</div>
                        <span>Joinable</span>
                    </div>
                </div>
                <div class="btn" @click="showDepositModal = true"><span>Create A Game</span></div>
            </div>
        </div>
        <div class="table-container">
            <table>
                <tr class="table-heading">
                    <th style="text-align: left">Players</th>
                    <th>Items</th>
                    <th>Total</th>
                    <th></th>
                </tr>
                <tr v-for="index in 3" :key="index">
                    <td>
                        <div v-if="isBlue(index)" class="avatar blue">
                            <img src="https://i.imgur.com/6HECU4E.png" alt="User Avatar" class="avatar">
                            Anunnaki Dev
                        </div>
                        <div v-else class="avatar red">
                            <img src="https://i.imgur.com/6HECU4E.png" alt="User Avatar" class="avatar">
                            Anunnaki Dev
                        </div>
                    </td>
                    <td>
                        <div class="items">
                            <img src="https://i.imgur.com/4LS5FYt.png" alt="">
                            <img src="https://i.imgur.com/IIbiiMJ.png" alt="">
                            <img src="https://i.imgur.com/tY1Kgfo.png" alt="">
                            <img src="https://i.imgur.com/jxDD7cA.png" alt="">
                            <div class="more-items">+10</div>
                        </div>
                    </td>
                    <td><div class="table-number"><span>$502.</span>32</div></td>
                    <td>
                        <div class="extra">
                            <div class="btn"><span>Join</span></div>
                            <div class="seen"></div>
                        </div>
                    </td>
                </tr>
                <tr>
                    <td>
                        <div class="avatar blue">
                            <img src="https://i.imgur.com/6HECU4E.png" alt="User Avatar" class="avatar">
                            Anunnaki Dev
                        </div>
                    </td>
                    <td>
                        <div class="items">
                            <img src="https://i.imgur.com/4LS5FYt.png" alt="">
                            <img src="https://i.imgur.com/IIbiiMJ.png" alt="">
                            <img src="https://i.imgur.com/tY1Kgfo.png" alt="">
                            <img src="https://i.imgur.com/jxDD7cA.png" alt="">
                            <div class="more-items">+10</div>
                        </div>
                    </td>
                    <td><div class="table-number"><span>$502.</span>32</div></td>
                    <td>
                        <div class="extra">
                            <div class="btn-joining"><img src="https://i.imgur.com/6HECU4E.png" alt="User Avatar" class="avatar"> Joining</div>
                            <div class="seen"></div>
                        </div>
                    </td>
                </tr>
                <tr>
                    <td>
                        <div class="avatar red">
                            <img src="https://i.imgur.com/6HECU4E.png" alt="User Avatar" class="avatar">
                            Anunnaki Dev
                        </div>
                    </td>
                    <td>
                        <div class="items">
                            <img src="https://i.imgur.com/4LS5FYt.png" alt="">
                            <img src="https://i.imgur.com/IIbiiMJ.png" alt="">
                            <img src="https://i.imgur.com/tY1Kgfo.png" alt="">
                            <img src="https://i.imgur.com/jxDD7cA.png" alt="">
                            <div class="more-items">+10</div>
                        </div>
                    </td>
                    <td><div class="table-number"><span>$502.</span>32</div></td>
                    <td>
                        <div class="extra">
                            <div class="btn-winner"><img src="https://i.imgur.com/6HECU4E.png" alt="User Avatar" class="avatar"> WINNER</div>
                            <div class="seen"></div>
                        </div>
                    </td>
                </tr>
            </table>
        </div>
        <DepositMethod v-show="showDepositModal" @close-modal="showDepositModal = false" />
        <SetCookie v-show="showCookieModal" @close-modal="showCookieModal = false" />
        <RobloxInventory v-show="showRobloxModal" @close-modal="showRobloxModal = false" />
    </div>
</template>

<script>
import DepositMethod from '~/components/DepositMethod.vue'
import SetCookie from '~/components/SetCookie.vue'
import RobloxInventory from '~/components/RobloxInventory.vue'
export default {
    components: { DepositMethod, SetCookie, RobloxInventory, },
    data() {
        return {
            showDepositModal: false,
            showCookieModal: false,
            showRobloxModal: false,
        }
    },
    methods: {
        isBlue: function(index) {
            return index % 2 == 0
        }
    }
}
</script>

<style scoped>
.extra {
    display: flex;
    gap: 15px;
    justify-content: center;
    align-items: center;
}
.seen {
    width: 42px;
    height: 39px;
    background: #292934;
    border: 1px solid #6F6E77;
    box-sizing: border-box;
    border-radius: 5px;
    position: relative;
}

.seen::after {
    content: '';
    position: absolute;
    display: block;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    height: 75%;
    width: 75%;
    background-image: url('https://www.freeiconspng.com/uploads/eye-outline-vector-icon--free-medical-icons-27.png');
    background-size: cover;
    background-position: center;
}
.items {
    display: flex;
    flex-direction: row;
    gap: 2px;
    justify-content: center;
}

.items > img {
    width: 70px;
    height: 70px;
}

.items > .more-items {
    font-family: Montserrat;
    font-style: normal;
    font-weight: bold;
    font-size: 25px;
    line-height: 30px;
    display: flex;
    align-items: center;
    color: #838383;
    margin-left: 15px;
}

table .avatar {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: Varela Round;
    font-weight: normal;
    font-size: 20px;
    line-height: 24px;
    color: #FFFFFF;
    text-transform: uppercase;
    position: relative;
}

table .avatar > img {
    width: 73px;
    height: 72px;
    border: 1px solid #414141;
}

table .avatar.red::after,
table .avatar.blue::after {
    content: '';
    position: absolute;
    display: block;
    width: 26px;
    height: 25px;
    top: 0;
    left: 0;
    background-size: cover;
    background-position: center;
}

table .avatar.red::after {
    background-image: url('https://i.imgur.com/zHWvSNt.png');
}

table .avatar.blue::after {
    background-image: url('https://i.imgur.com/C08dmIT.png');
}

.table-container {
    margin: 15px;
}

table {
    width: 100%;
    border-collapse: collapse;
    border-top: 1px solid #313439;
}

tr {
    height: 99px;
}

tr:nth-child(even){
    background: linear-gradient(0deg, #23212D, #23212D), #23212D;
}

tr:nth-child(odd) {
    background: linear-gradient(0deg, #1E1E29, #1E1E29), #23212D;
}

tr.table-heading {
    height: 50px;
    text-align: left;
    background: none;
    background-color: var(--primary-bg);
}

tr.table-heading > th {
    font-family: Varela Round;
    font-weight: normal;
    font-size: 14px;
    line-height: 17px;
    color: #A5A2A2;
    padding-left: 30px;
    text-transform: uppercase;
    text-align: center;
}

td {
    padding-left: 15px;
}

td .btn {
    width: 96px;
    height: 39px;
}

.header {
    height: 95px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 50px;
}

.header > .left > h1 {
    width: 313px;
    height: 49px;
    font-family: Montserrat;
    font-weight: 600;
    font-size: 40px;
    line-height: 49px;
    color: #FFFFFF;
    text-transform: uppercase;
}

.header > .right {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 100px;
}

.header-stats {
    display: flex;
    align-items: center;
    flex-direction: row;
    gap: 30px;
}

.stat {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    color: #868181;
    text-transform: uppercase;
}

.stat > span {
    font-family: Montserrat;
    font-weight: 600;
    font-size: 15px;
    line-height: 18px;
    color: #868181;
}

.number {
    font-family: Montserrat;
    font-weight: 600;
    font-size: 30px;
    line-height: 37px;
}

.table-number {
    font-family: Montserrat;
    font-style: normal;
    font-weight: 600;
    font-size: 24px;
    line-height: 29px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #868181;
}

.table-number > span,
.number > span {
    color: #fff;
}

.main-page {
    height: auto;
    overflow-y: auto; /* Delete this line if you don't want scrolling on this page (for the table) */
}
</style>
