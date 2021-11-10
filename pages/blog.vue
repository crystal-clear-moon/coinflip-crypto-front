<template>
    <div class="main-page">
        <div class="main-page-content">
            <h1>Blog</h1>
            <h3>Blog <span>1.01 -</span> Coinflip.pet Admin Team</h3>
            <div class="blog-content">
                <h4>Can I play at an online casino if my country is restricted?</h4>
                <p>
                    As you already know, the digital space is filled with all kinds of gambling sites that operate under different kinds of licenses and regulations, depending on the region. So, it’s very much possible that some regulations restrict you from accessing specific online casinos because your country doesn’t allow them. 
                </p>
                <p>
                    In general, if you live in a “restricted” country, you as a player can not sign up, access some games to win real money or deposit. Now, some countries can be entirely restricted while others can be partially restricted. 
                </p>
                <p>
                    Depending on how much your country is or isn’t restricted, some players will not be allowed to access the bonus offers, and others will not be able to access instant withdrawal casinos, and so on and so on. 
                </p>
                <p>
                    With all this in mind, the message you should take from this is that you need to find out whether your preferred online casino has been restricted before signing up and playing casino games. The last thing you want is to get into some legal trouble when your intentions were pure from the start. 
                </p>
                <h4>The UK</h4>
                <p>
                    As of June of 2021, online gambling is legal in the UK and regulated by the Gambling Commission. There are a myriad of games that fall under the jurisdiction of the Gambling Commission, from poker and bingo to sports bettings. 
                </p>
                <p>
                    One interesting fact about online gambling in the UK is that you can cash out your winnings without paying taxes. Yes, you read that correctly. Online gamblers don’t pay taxes in the UK, which honestly makes it one of the best places in the world to gamble online. 
                </p>
            </div>
        </div>
    </div>
</template>

<style scoped>

.blog-content {
    margin-top: 30px;
    font-family: Montserrat;
    font-style: normal;
    font-weight: 500;
    font-size: 25px;
    line-height: 30px;
}

h1, h3 {
    text-transform: uppercase;
    text-align: center;
    margin: 0;
}

.blog-content p, h3, h1 {
    color: #fff;
}

.blog-content h4, h3 > span {
    color: #A2262B;
}

h1 {
    font-family: Montserrat;
    font-style: normal;
    font-weight: bold;
    font-size: 70px;
    line-height: 85px;
    position: relative;
    display: inline-block;
    margin-bottom: 25px;
}

h1::after {
    content: '';
    position: absolute;
    display: block;
    width: calc(100% + 160px);
    height: 1px;
    left: 50%;
    bottom: -19px;
    background-color: #E32B3C;
    transform: translateX(-50%);
}

h3 {
    font-family: Montserrat;
    font-style: normal;
    font-weight: 500;
    font-size: 25px;
    line-height: 30px;
    margin-top: 25px;
}

h4 {
    margin: 0;
}

p {
    margin: 20px 0;
}

.main-page {
    display: flex;
    height: 100%;
    padding: 40px;
    overflow-y: auto;
    position: relative;
    overflow-x: hidden;
}

.main-page::before {
    content: '';
    position: absolute;
    display: block;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: #171721;
    z-index: 1;
}

.main-page::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    display: flex;
    height: 100vh;
    max-height: 100vh;
    width: 100vw;
    background-image: url('/images/pattern-bg.jpg');
    background-size: cover;
    background-position: center;
    opacity: 0.1;
    z-index: 2;
}

.main-page-content {
    position: relative;
    z-index: 10;
    display: flex;
    flex-direction: column;
    align-items: center;
    
}
</style>