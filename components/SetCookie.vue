<template>
    <transition name="modal-fade">
        <div class="modal-overlay" @click="$emit('close-modal')">
            <div class="modal" @click.stop>
                <h3>Set your cookie</h3>
                <div class="modal-content">
                    <div class="inner-modal">
                        <h3>Cookie</h3>
                        <input type="text" placeholder="Type here...">
                    </div>
                </div>
                <div class="modal-footer">
                    <div class="modal-footer-content">
                        <h4>Click here to find out how to find your cookie</h4>
                        <div class="btn"><span>Save</span></div>
                    </div>
                </div>
            </div>
            <!-- <div class="close" @click="$emit('close-modal')">
                <img class="close-img" src="~/assets/images/close-icon.svg" alt="" />
            </div> -->
        </div>
    </transition>
</template>

<script>
export default {}
</script>

<style scoped>
input {
    background: #171721;
    border-radius: 7px;
    width: 825px;
    outline: none;
    border: none;
    height: 40px;
    font-size: 18px;
    line-height: 22px;
    color: rgba(255, 255, 255, 0.6);
    font-family: Montserrat;
    font-style: normal;
    font-weight: bold;
    padding-left: 5px;
}

input::placeholder {
    padding-left: 5px;
}
.inner-modal {
    position: absolute;
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    height: 100%;
    width: 100%;
    gap: 12px;
    z-index: 100;
    padding-left: 28px;
}

.modal-footer {
    position: relative;
    z-index: 60;
    width: 876px;
}

.modal-footer .btn {
    width: 114px;
    height: 44px;
    box-shadow: 0px 4px 4px 6px rgba(0, 0, 0, 0.25);
}

.modal-footer .btn > span {
    font-family: Montserrat;
    font-style: normal;
    font-weight: bold;
    font-size: 23px;
    line-height: 28px;
    text-align: center;
}

.modal-footer-content {
    padding: 10px 40px 10px 28px;
    display: flex;
    align-items: center;
    gap: 50px;
    height: 100%;
    justify-content: space-between;
}

.modal > h3 {
    margin-bottom: 10px;
}

h3,
h4 {
    z-index: 60;
    margin: 0;
}

h3 {
    font-family: Montserrat;
    font-style: normal;
    font-weight: bold;
    font-size: 25px;
    line-height: 30px;
    color: #FFFFFF;
    opacity: 0.8;
    text-transform: uppercase;
    text-align: center;
}

h4 {
    font-family: Montserrat;
    font-style: normal;
    font-weight: bold;
    font-size: 18px;
    line-height: 22px;
    letter-spacing: 0.12em;
    color: #FFFFFF;
    opacity: 0.6;
}

.modal-content {
    width: 876px;
    height: 288px;
    background: #23212D;
    border: 1px solid #929292;
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
    height: 430px;
    width: 875px;
    margin-top: 10%;
    z-index: 50;
    border: 1px solid #5C5C5C;
    position: relative;
    border-radius: 10px;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
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
    margin: 10% 0 0 16px;
    cursor: pointer;
}

.close-img {
    width: 25px;
}

.check {
    width: 150px;
}

h6 {
    font-weight: 500;
    font-size: 28px;
    margin: 20px 0;
}

p {
    /* font-weight: 500; */
    font-size: 16px;
    margin: 20px 0;
}

button {
    background-color: #ac003e;
    width: 150px;
    height: 40px;
    color: white;
    font-size: 14px;
    border-radius: 16px;
    margin-top: 50px;
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