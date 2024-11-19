<template>
  <Transition name="fade" mode="out-in" appear>
    <div v-if="!isForm" class="hello-parent flex flex-col" key="Hello">
      <svg class="hello-word" width="365" height="350" viewBox="0 0 365 277">
        <Letter v-for="(letter, index) in name" :letter="letter" :key="index"/>
      </svg>
      <p
        class="text-white tracking-[0.3rem] text-lg pt-4 mount-anime pointer-events-none"
      >
        Web-developer / Freelancer
      </p>
    </div>
    <div
      v-else
      id="sheet"
      class="bg-white bg-opacity-0 w-[365px] h-[321px] pb-4 grid grid-cols-2 grid-rows-[1fr_1fr_3fr_1fr] gap-3 place-items-center relative"
    >
      <div class="form mount-anime-name z-10">
        <input
          v-model="nameValue"
          maxlength="15"
          type="text"
          name="text"
          autocomplete="off"
          required
        />
        <label for="text" class="label-name">
          <span class="content-name"> Имя </span>
        </label>
      </div>
      <div class="form mount-anime-subject z-10">
        <input
          v-model="subjectValue"
          maxlength="18"
          type="text"
          name="text"
          autocomplete="off"
          required
        />
        <label for="text" class="label-name">
          <span class="content-name"> Тема сообщения </span>
        </label>
      </div>
      <div class="form mount-anime-mail col-span-2">
        <input
          v-model="emailValue"
          type="text"
          name="text"
          maxlength="30"
          autocomplete="off"
          required
        />
        <label for="text" class="label-name">
          <span class="content-name"> Почта </span>
        </label>
      </div>
      <div
        class="form mount-anime-textarea row-start-3 row-end-4 col-start-1 col-end-3"
      >
        <textarea
          v-model="textareaValue"
          maxlength="200"
          spellcheck="false"
          placeholder="Сообщение"
          type="text"
          name="text"
          autocomplete="off"
          required
          class="max-md:text-[16px]"
        ></textarea>
        <label for="text" class="label-name">
          <!-- <span class="content-name"> Содержание </span> -->
        </label>
      </div>

      <button
        @click="sendForm()"
        class="row-start-4 row-end-5 col-start-1 col-end-3 bg-sky-500 bg-opacity-1 transition-all w-[100%] mount-anime-send rounded-[0.5rem] text-white hover:bg-sky-700"
      >
        Отправить
      </button>
      <div
        id="bot"
        class="bg-white bg-opacity-0 absolute w-[80%] h-[3.7rem] right-2 top-0 z-0 bot-animation grid grid-cols-[4fr_1fr]"
      >
        <div
          id="messagebox"
          class="bg-white h-10 message-borders w-[95%] flex items-center bot-message-anime"
        >
          <p class="px-2 leading-[1rem]">{{ botResponse }}</p>
        </div>
        <img
          src="../images/bot.png"
          alt="Bot"
          class="object-contain w-[100%] col-start-2 col-end-3"
        />
      </div>
    </div>
  </Transition>
  <button
    class="button-64 mount-anime-btn mt-4"
    role="button"
    @click="changeState"
  >
    <span class="text">{{ btnState }}</span>
  </button>
</template>

<script lang="ts">
import axios from "axios";
import Letter from "./Letter.vue";


export default {
  props: [""],
  components: { Letter },
  data() {
    return {
      // isBot: false,
      isForm: false,
      nameValue: "",
      subjectValue: "",
      emailValue: "",
      textareaValue: "",
      isSendButtonClicked: false,
      botResponse: "Привет, я помогу тебе заполнить форму, бип.",
      name: "ARTURO"
    };
  },
  methods: {
    changeState(): void {
      this.isForm = !this.isForm;
    },
    inputClean() {
      this.nameValue = "";
      this.subjectValue = "";
      this.emailValue = "";
      this.textareaValue = "";
    },
    changeSendButtonState() {
      if (!this.isSendButtonClicked) {
        this.isSendButtonClicked = !this.isSendButtonClicked;
        // setTimeout(() => {
        //   this.isSendButtonClicked = !this.isSendButtonClicked;
        // }, 1000);
      }
    },
    async sendRequest() {
      try {
        const options = {
          method: "POST",
          url: "https://api.telegram.org/bot7478100790:AAE3t_2wrz4VmYZyqMbrsXTDMR0S7eFlB-Y/sendMessage",
          headers: {
            accept: "application/json",
            "content-type": "application/json",
          },
          data: {
            text: `<b>Name:</b>\n${this.nameValue}\n<b>Subject:</b>\n${this.subjectValue}\n<b>Email:</b>\n${this.emailValue}\n<b>Text:</b>\n${this.textareaValue}`,
            disable_web_page_preview: false,
            disable_notification: false,
            parse_mode: "HTML",
            reply_to_message_id: null,
            chat_id: "501766778",
          },
        };

        await axios.request(options);
        this.inputClean();
      } catch (error) {
        console.log(error);
        this.botResponse = "Что-то сломалось! Проверь интернет.";
      }
    },
    botResponseOptions() {
      const emailCheck = this.emailValue.split("@").length;
      if (
        this.nameValue &&
        this.textareaValue &&
        this.subjectValue &&
        emailCheck !== 2 &&
        this.isSendButtonClicked
      )
        return "Попробуй формат почты example@index.ru";
      else if (
        this.nameValue &&
        this.textareaValue &&
        this.subjectValue &&
        emailCheck === 2 &&
        this.isSendButtonClicked
      )
        return "Готово! Я отправил все создателю.";
      return "Заполни все поля.";
    },
    check() {
      console.log(this.nameValue);
      console.log(this.subjectValue);
      const emailCheck = this.emailValue.split("@").length;
      console.log(this.emailValue);
      console.log(emailCheck);
      console.log(this.textareaValue);
    },
    sendForm() {
      this.changeSendButtonState();
      this.botResponse = this.botResponseOptions();
      const emailCheck = this.emailValue.split("@").length;
      if (
        emailCheck === 2 &&
        this.nameValue &&
        this.textareaValue &&
        this.subjectValue
      ) {
        this.sendRequest();
      }
    },
  },
  computed: {
    btnState() {
      return this.isForm ? "Вернуться" : "Напиши мне";
    },
  },
};
</script>
<style scoped>
.button-64 {
  align-items: center;
  background-image: linear-gradient(
    144deg,
    #00ff48,
    #f9f942 30%,
    #ff003c 60%,
    #0055ff
  );
  border: 0;
  border-radius: 17px;
  /* box-shadow: rgba(151, 65, 252, 0.2) 0 15px 30px -5px; */
  box-sizing: border-box;
  color: #ffffff;
  display: flex;
  /* font-family: Phantomsans, sans-serif; */
  font-size: 20px;
  justify-content: center;
  line-height: 0.8rem;
  max-width: 10rem;
  min-width: 140px;
  padding: 3px;
  text-decoration: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  white-space: nowrap;
  cursor: pointer;
}

.button-64:active,
.button-64:hover {
  outline: 0;
  color: #000;
}

.button-64 span {
  background-color: rgb(0, 0, 0);
  padding: 16px 24px;
  border-radius: 17px;
  width: 100%;
  height: 100%;
  transition: 300ms;
}

.button-64:hover span {
  background: none;
}


html,
body,
.hello-parent {
  height: 100%;
  width: 100%;
  margin: 0;
}

*,
*::after,
*::before {
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.message-borders {
  border-radius: 1rem 1rem 0 1rem;
}

.bot-animation {
  transform: translateY(-3.4rem);
  -webkit-animation: bot-move 10s ease;
  animation: bot-move 10s ease;
}

@-webkit-keyframes bot-move {
  0% {
    opacity: 0;
    transform: translateY(0);
  }
  30% {
    opacity: 0;
    transform: translateY(0);
  }
  40% {
    transform: translateY(-3.4rem);
    opacity: 1;
  }
  50% {
  }
  100% {
    transform: translateY(-3.4rem);
  }
}

@keyframes bot-move {
  0% {
    opacity: 0;
    transform: translateY(0);
  }
  30% {
    opacity: 0;
    transform: translateY(0);
  }
  40% {
    transform: translateY(-3.4rem);
    opacity: 1;
  }
  50% {
  }
  100% {
    transform: translateY(-3.4rem);
  }
}

.bot-message-anime {
  /* transform: translateX(100px) translateY(15px) scale(10%) ; */
  transition-property: all;
  /* transition: 1s ease; */
  -webkit-animation: bot-message-move 10s ease;
  animation: bot-message-move 10s ease;
  /* width: 95%; */
}

@-webkit-keyframes bot-message-move {
  0% {
    opacity: 0;
  }
  40% {
    opacity: 0;
    transform: translateX(100px) translateY(15px) scale(10%);
  }
  45% {
    opacity: 1;
    transform: translateX(0) translateY(0) scale(100%);
  }
}

@keyframes bot-message-move {
  0% {
    opacity: 0;
  }
  40% {
    opacity: 0;
    transform: translateX(100px) translateY(15px) scale(10%);
  }
  45% {
    opacity: 1;
    transform: translateX(0) translateY(0) scale(100%);
  }
}

.form {
  width: 100%;
  position: relative;
  height: 60px;
  overflow: hidden;
  border-radius: 0.5rem;
}

.form:nth-child(4) {
  height: 100%;
}

.form input,
.form textarea {
  width: 100%;
  height: 100%;
  color: #fff;
  padding-top: 20px;
  border: none;
  background-color: #484848;
  text-indent: 0.3rem;
}

.form textarea {
  padding-top: 0.2rem;
  line-height: 1rem;
  padding-left: 0.2rem;
  font-size: small;
  resize: none;
}

@media (max-width: 768px) {
  .form textarea {
    font-size: 16px;
  }
}

.form label {
  position: absolute;
  bottom: 0px;
  left: 0px;
  width: 100%;
  height: 100%;
  pointer-events: none;
  /* border-bottom: 1px solid white; */
}
.form label::after {
  content: "";
  position: absolute;
  bottom: -1px;
  left: 0px;
  width: 100%;
  height: 100%;
  border-bottom: 4px solid;
  -o-border-image: linear-gradient(
      to right,
      #00ff48 0%,
      #f9f942 25%,
      #ff003c 50%,
      #0055ff 90%
    )
    5;
  border-image: linear-gradient(
      to right,
      #00ff48 0%,
      #f9f942 25%,
      #ff003c 50%,
      #0055ff 90%
    )
    5;
  transform: translateX(-100%);
  transition: all 0.3s ease;
}

.content-name {
  position: absolute;
  bottom: 0px;
  left: 0.5rem;
  padding-bottom: 5px;
  transition: all 0.4s ease;
  color: white;
}
.form input:focus {
  outline: none;
}
.form textarea:focus {
  outline: none;
}
.form input:focus + .label-name .content-name,
.form input:valid + .label-name .content-name {
  transform: translateY(-130%);
  font-size: 14px;
  left: 0.3rem;
  color: #fff;
}

/* .form input:invalid + .label-name .content-name {
  transform: translateY(-130%);
  font-size: 14px;
  left: 0.3rem;
  color: #fff;
} */

.form textarea:focus + .label-name .content-name,
.form textarea:valid + .label-name .content-name {
  transform: translateY(-130%);
  font-size: 14px;
  left: 0.3rem;
  color: #fff;
}
.form input:focus + .label-name::after,
.form input:valid + .label-name::after {
  transform: translateX(0%);
}

.form textarea:focus + .label-name::after,
.form textarea:valid + .label-name::after {
  transform: translateX(0%);
}

.fade-enter-active {
  transition: opacity 1s ease;
}

.fade-leave-active {
  transition: opacity 1s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

@media (min-width: 768px) {
  .button-64 {
    font-size: 24px;
    min-width: 196px;
  }
}
.mount-anime-name {
  /* animation-delay: 3s; */
  opacity: 1;
  -webkit-animation: mount-move 1.5s ease;
  animation: mount-move 1.5s ease;
}
.mount-anime-subject {
  /* animation-delay: 3s; */
  opacity: 1;
  -webkit-animation: mount-move 1.7s ease;
  animation: mount-move 1.7s ease;
}
.mount-anime-mail {
  /* animation-delay: 3s; */
  opacity: 1;
  -webkit-animation: mount-move 2s ease;
  animation: mount-move 2s ease;
}
.mount-anime-textarea {
  /* animation-delay: 3s; */
  opacity: 1;
  -webkit-animation: mount-move 2.2s ease;
  animation: mount-move 2.2s ease;
}

.mount-anime-send {
  /* animation-delay: 3s; */
  opacity: 1;
  -webkit-animation: mount-move 2.5s ease;
  animation: mount-move 2.5s ease;
}

.mount-anime-btn {
  /* opacity: 1; */
  -webkit-animation: mount-move 4s ease;
  animation: mount-move 4s ease;
}

@-webkit-keyframes mount-move {
  0% {
    transform: translateY(40px);
    opacity: 0;
  }

  40% {
    transform: translateY(40px);
    opacity: 0;
  }
  60% {
    /* transform: translateY(5px); */
    opacity: 1;
  }
  100% {
    opacity: 1;
  }
}

@keyframes mount-move {
  0% {
    transform: translateY(40px);
    opacity: 0;
  }

  40% {
    transform: translateY(40px);
    opacity: 0;
  }
  60% {
    /* transform: translateY(5px); */
    opacity: 1;
  }
  100% {
    opacity: 1;
  }
}

.red-dot {
  stroke-width: 0px;
  stroke-linecap: round;
  -webkit-animation: red-dot-grow 8s ease-out forwards;
  animation: red-dot-grow 8s ease-out forwards;
  -webkit-animation-delay: 1s;
  animation-delay: 1s;
}

.green-dot {
  stroke-width: 0px;
  stroke-linecap: round;
  -webkit-animation: green-dot-grow 8s ease-out forwards;
  animation: green-dot-grow 8s ease-out forwards;
  -webkit-animation-delay: 1.1s;
  animation-delay: 1.1s;
}

@-webkit-keyframes green-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 24px;
  }
  100% {
    stroke-width: 24px;
  }
}

@keyframes green-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 24px;
  }
  100% {
    stroke-width: 24px;
  }
}
.blue-dot {
  stroke-width: 0px;
  stroke-linecap: round;
  -webkit-animation: blue-dot-grow 8s ease-out forwards;
  animation: blue-dot-grow 8s ease-out forwards;
  -webkit-animation-delay: 1.2s;
  animation-delay: 1.2s;
}

@-webkit-keyframes blue-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 14px;
  }
  100% {
    stroke-width: 14px;
  }
}

@keyframes blue-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 14px;
  }
  100% {
    stroke-width: 14px;
  }
}
.yellow-dot {
  stroke-width: 0px;
  stroke-linecap: round;
  -webkit-animation: yellow-dot-grow 8s ease-out forwards;
  animation: yellow-dot-grow 8s ease-out forwards;
  -webkit-animation-delay: 1.3s;
  animation-delay: 1.3s;
}

@-webkit-keyframes yellow-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 4px;
  }
  100% {
    stroke-width: 4px;
  }
}

@keyframes yellow-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 4px;
  }
  100% {
    stroke-width: 4px;
  }
}

@-webkit-keyframes red-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 34px;
  }
  100% {
    stroke-width: 34px;
  }
}

@keyframes red-dot-grow {
  0% {
    stroke-width: 0px;
  }
  15% {
    stroke-width: 0px;
  }
  20% {
    stroke-width: 34px;
  }
  100% {
    stroke-width: 34px;
  }
}



@-webkit-keyframes r-two-stroke {
  0% {
    stroke-dashoffset: 43px;
  }
  80% {
    stroke-dashoffset: 10px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}

@keyframes r-two-stroke {
  0% {
    stroke-dashoffset: 43px;
  }
  80% {
    stroke-dashoffset: 10px;
  }
  100% {
    stroke-dashoffset: 0px;
  }
}




</style>
