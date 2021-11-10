<template>
    <div class="primary-content">
        <div class="sidebar">
            <div class="sidebar-heading" style="background-image: url('/images/pet.png')">
            </div>
            <Chat />
        </div>
        <div class="page-body">
                <div class="nav">
                    <a href="#">Provably Fair</a>
                    <a href="#">FAQ</a>
                    <a href="#">Privacy Policy</a>
                    <a href="#">Support</a>
                    <a href="#">Blog</a>
                    <a href="#">Discord</a>
                </div>
                <div class="user-bar">
                    <div class="page">Coinflip <div class="amount"><span>5.420.32$</span></div></div>
                    <div class="user-info">
                        <div class="avatar">
                            AnunnakiDev
                            <img src="https://i.imgur.com/6HECU4E.png" alt="User Avatar" class="avatar">
                        </div>
                        <div class="logout"><img src="/images/logout.png" alt="Logout"></div>
                    </div>
                </div>
                <Nuxt />
            </div>
    </div>
</template>

<script>
import Chat from '@/components/Chat.vue'
export default {
    components: {
        Chat
    }
}
</script>

<style scoped>
.primary-content {
    width: 100vw;
    height: 100vh;
    display: flex;
}

.nav {
    height: 31px;
    background-color: #171721;
    padding: 7px 46px;
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 42px;
}

.nav > a {
    color: #797979;
    font-family: Montserrat;
    font-style: normal;
    font-weight: 600;
    font-size: 15px;
    line-height: 18px;
    text-decoration: none;
    height: 18px;
}

.user-bar {
    padding: 0px 46px;
    height: 50px;
    min-height: 50px;
    max-height: 50px;
    background-color: #1E1E29;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
}

.user-bar > .page {
    font-family: Montserrat;
    font-weight: bold;
    font-size: 15px;
    line-height: 18px;
    display: flex;
    align-items: center;
    color: #FFFFFF;
    gap: 10px;
    text-transform: uppercase;
    position: relative;
}

.user-bar > .page::after {
    content: '';
    position: absolute;
    display: block;
    width: calc(100% + 20px);
    height: 1px;
    left: 50%;
    bottom: -15px;
    background-color: #E32B3C;
    transform: translateX(-50%);
}

.user-info {
    display: flex;
    align-items: center;
    gap: 10px;
}

.page > .amount {
    background-image: url('https://i.imgur.com/Y7Uf42E.png');
    background-size: cover;
    background-position: center;
    box-shadow: 0px 4px 4px 3px rgba(0, 0, 0, 0.25);
    border-radius: 5px;
    overflow: hidden;
    position: relative;
    width: 73px;
    height: 26px;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1;
}

.page > .amount::after {
    content: '';
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(200, 19, 40, 0.5);
    z-index: 2;
}

.page > .amount > span {
    z-index: 3;
    font-family: Montserrat;
    font-weight: bold;
    font-size: 10px;
    line-height: 12px;
    text-align: center;
}
</style>