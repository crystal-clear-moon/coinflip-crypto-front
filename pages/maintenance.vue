<template>
    <div class="primary">
        <img src="/images/pet.png" alt="">
        <h1>The site is currently under going maintenance...</h1>
        <h4>We will be back soon, check our social media for updates!</h4>
        <div class="socials">
            <img src="/images/twitter.svg" alt="">
            <img src="/images/twitter.svg" alt="">
            <img src="/images/twitter.svg" alt="">
        </div>
        <div class="btn"><span>Admin Login</span></div>
    </div>
</template>

<script>
export default {
    layout: 'maintenance'
}
</script>

<style scoped>
.btn {
    position: absolute;
    right: 10px;
    top: 10px;
    width: 165px;
    height: 44px;
}

.btn > span {
    font-size: 18px;
    line-height: 22px;
}
.primary {
    display: flex;
    height: 100%;
    width: 100%;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 15px;
    position: relative;
    z-index: 5;
}

.primary > img {
    width: 350px;
    height: auto;
}

h1, h4 {
    margin: 0;
    padding: 0;
}

h1 {
    font-family: Montserrat;
    font-style: normal;
    font-weight: bold;
    font-size: 70px;
    line-height: 85px;
    color: #FFFFFF;
}

h4 {
    font-family: Montserrat;
    font-style: normal;
    font-weight: bold;
    font-size: 25px;
    line-height: 30px;
    letter-spacing: 0.12em;
    color: #FFFFFF;
}

.socials {
    display: flex;
    gap: 60px;
}
</style>