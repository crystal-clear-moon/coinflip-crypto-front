<template>
    <div class="chat">
        <div class="chat-header">
            <div class="chat-online"><span>3</span>Online</div>
            <div class="chat-title">Live Chat</div>
        </div>
        <div class="chat-container">
            <div class="chat-messages">
                <div class="message-container" v-for="index in 14" :key="index">
                    <div class="message-info">
                        <img src="https://i.imgur.com/6HECU4E.png" alt="User Avatar" class="avatar">
                        <div class="message">
                            <div class="user">ANUNNAKI DEV</div>
                            <div class="message-text">What a great website!</div>
                        </div>
                    </div>
                    <div class="message-time">15:55</div>
                </div>
            </div>
            <div class="chat-box">
                <div class="message-box">
                    <textarea type="text" class="message-input" placeholder="Login to use chat..."></textarea>
                    <div class="message-submit"><img src="https://i.imgur.com/uiAFg8i.png" alt="Send"></div>
                    <div class="message-face"><img src="https://i.imgur.com/Qnyufu1.png" alt="Face"></div>
                </div>
                <div class="chat-info">
                    <a href="#">Chat Rules</a>
                    <a href="#">Room: English</a>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.chat-info {
    width: 100%;
    display: flex;
    justify-content: center;
    gap: 120px;
}
.chat-info > a {
    font-family: Varela Round;
    font-size: 10px;
    text-decoration: none;
    color: #C4C4C4;
    text-transform: uppercase;
}
.chat-box {
    max-height: 140px;
    height: 100%;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    padding: 15px;
    gap: 10px;
}

.chat-container {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    flex-grow: 1;
}
.chat {
    background-color: var(--chat-bg);
    /* height: calc(100% - var(--sidebar-head-height)); */
    overflow: hidden;
    font-family: Varela Round, sans-serif;
    font-weight: 400;
    display: flex;
    flex-direction: column;
    flex-grow: 1;
}

.chat-header {
    padding: 10px 8px;
    position: relative;
    font-size: 17px;
}

.chat-title {
    position: absolute;
    color: #fff;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    text-transform: uppercase;
}

.chat-online {
    color: rgba(var(--chat-counter-title));
}
.chat-online > span {
    margin-right: 5px;
    color: var(--chat-counter);
}

.chat-messages {
    width: 100%;
    flex-grow: 1;
    overflow-y: auto;
    border-top: 1px solid #E32B3C;
}

.chat-messages::-webkit-scrollbar {
  width: 0;
  height: 0;
}

::-webkit-scrollbar-thumb {
  background: rgba(0, 0, 0, 0);
}

::-webkit-scrollbar-track {
  background: rgba(0, 0, 0, 0);
}

.message-container {
    padding: 10px 8px;
    position: relative;
}

.message-container:nth-child(even) {
    background-color: #1B1B25;
}

.message-container > .message-time {
    position: absolute;
    font-family: Varela Round;
    font-size: 13px;
    line-height: 16px;
    color: #929292;
    right: 10px;
    top: 50%;
    transform: translate(0, -50%);
}

.message-container > .message-info > .avatar {
    height: 40px;
    width: 40px;
    border-radius: 100px;
}

.message-container > .message-info {
    display: flex;
    align-items: center;
    gap: 10px;
}

.message-info > .message > .user {
    color: #D6D6D6;
    text-transform: uppercase;
    font-size: 13px;
    line-height: 16px;
}

.message-info > .message > .message-text {
    color: #929292;
    font-size: 13px;
    line-height: 16px;
}

.message-box {
  width: 306px;
  background: #1B1B25;
  position: relative;
  border-radius: 5px;
  height: 51px;
  border: 1px solid #5A5A5A;
  overflow: hidden;
}

.message-box .message-input {
  background: none;
  border: none;
  outline: none !important;
  resize: none;
  font-size: 15px;
  margin: 0;
  width: 215px;
  height: 51px;
  color: #9D9D9D;
  padding: 2px 5px;
}

.message-box textarea::placeholder {
    font-family: Varela Round;
    font-size: 20px;
    line-height: 24.08px;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    left: 15px;
    color: #9D9D9D;
}

.message-box textarea:focus::-webkit-placeholder {
    color: transparent;
}

.message-submit,
.message-face {
    position: absolute;
    z-index: 1;
    top: 50%;
    transform: translateY(-50%);
    border: none;
    outline: none !important;
    cursor: pointer;
}

.message-box .message-submit {
    right: 50px;
}

.message-face {
    right: 18px;
}

.message-submit, .message-submit > img, .message-face, .message-face > img {
    height: 18px;
    width: 17px;
}
</style>