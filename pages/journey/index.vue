<template>
  
  <div class="th-message ">
    <h2 class="delayed-fade-th">
      เค้าอยากบอกว่า ตลอด2ปีที่ผ่านมา <br> เค้ามีความสุขมากๆที่มีเธอเข้ามาในชีวิต
      ต่อไปนี้มันอาจจะไม่ง่ายเหมือนที่ผ่านๆมา แต่เค้าสัญญาว่าจะทำทุกอย่างให้ดีที่สุด <br>
      เค้ารักเธอมากที่สุดเลยคนเก่งของเค้า💖
    </h2>
   
  </div>
  <div>
    <instragramPost class="delayed-fade" avatarSrc="/user1.jpg" username="Nannat" imageSrc="/firstDate.jpg"
      caption="Fisrt date. ❤️" location="Klang Plaza ,Nakhonratchasima Thailand" date="12 March 2022" />
    <instragramPost class="delayed-fade" avatarSrc="/user2.jpg" username="Peter" imageSrc="/firstDate2.jpg"
      caption="First met. 💖" location="Klang Plaza ,Nakhonratchasima Thailand" date="12 March 2022" />
    <instragramPost class="delayed-fade" avatarSrc="/user1.jpg" username="Nannat" imageSrc="/nan18.jpg"
      caption="First cake.🎂" location="Home ,Thailand" date="31 March 2022" />
    <instragramPost class="delayed-fade" avatarSrc="/user.jpg" username="Memmories" imageSrc="/holdHand.jpg"
      caption="🧑🏻‍🤝‍👩🏼🧑🏻‍🤝‍👩🏼🧑🏻‍🤝‍👩🏼🧑🏻‍🤝‍👩🏼🧑🏻‍🤝‍👩🏼" location="Nakhonratchasima,Thailand"
      date="22 May 2022" />


    <instragramPost class="delayed-fade" avatarSrc="/user.jpg" username="Memmories" imageSrc="/bigMountain.jpg"
      caption="First trip.🌄🌄🌄" location="Khoayai ,Nakhonratchasima,Thailand" date="14 December 2022" />
    <instragramPost class="delayed-fade" avatarSrc="/user.jpg" username="Memmories" imageSrc="/pt20.jpg"
      caption="Peter's Birthday." location="Nakhonratchasima,Thailand" date="29 December 2022" />
    <instragramPost class="delayed-fade" avatarSrc="/user.jpg" username="Memmories" imageSrc="/beach.jpg"
      caption="Beach ,Sunset, You. " location="Ra yong,Thailand" date="4 May 2023" />
    <instragramPost class="delayed-fade" avatarSrc="/user.jpg" username="Memmories" imageSrc="/jjMall.jpg"
      caption="Bangkok.💕💕💕" location="JJ Mall, Bang Kok, Thailand" date="12 November 2023" />
    <instragramPost class="delayed-fade" avatarSrc="/user.jpg" username="Memmories" imageSrc="/nannat20.jpg"
      caption="21 Years old's Nannat🎂🎂🎂" location="Banjong, Bang Kok, Thailand" date="31 March 2024" />
  </div>
</template>

<script>
import InstragramPost from '~/components/instragramPost.vue'

export default {
  components: {
    InstragramPost
  },
  props: {
    avatarSrc: {
      type: String,
      default: "/public/cat.jpg"
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Mitr:wght@400;500;600&display=swap');

body {
  background-color: #fafafa;

}

.th-message {
  text-align: center;
  margin: 20px auto; /* Add auto margin to horizontally center */
  max-width: 80%;
  margin-top: 40px; /* Set a maximum width to prevent stretching */
}

.aniversary-message {

  margin: 20px;
  font-family: 'Mitr', sans-serif;
  background-color: #fff0f5;
  /* Light pink background */
  padding: 20px;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  margin-bottom: 20px;
  animation: fadeIn 2s;
  font-size: 1.5em;
  /* Increase font size for emphasis */
  color: #ff69b4;
  /* Pink text color */
  border: 2px solid #ff1493;
  /* Darker pink border */
  position: relative;
  /* For the decoration positioning */
}



.aniversary-message:before {
  left: 10px;
}

.aniversary-message:after {
  right: 10px;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

.delayed-fade-th {
  font-size: 15px;
  opacity: 0;
  animation: fadeIn 2s ease-in 1s forwards;
  font-family: 'Mitr', sans-serif;
  background-color: #fff0f5; /* Light pink background */
  padding: 20px;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  color: #ff69b4; /* Pink text color */
  border: 2px solid #ff1493; /* Darker pink border */
  display: inline-block;
}

@keyframes bounce {

  0%,
  20%,
  50%,
  80%,
  100% {
    transform: translateY(0);
  }

  40% {
    transform: translateY(-10px);
  }

  60% {
    transform: translateY(-5px);
  }
}

.delayed-fade {
  opacity: 0;
  animation: fadeIn 2s ease-in 8s forwards;
}

@media (max-width: 768px) {
  .aniversary-message {
    font-size: 10px;
    /* Adjust font size for iPad */
    padding: 15px;
    /* Adjust padding for iPad */
  }

  .aniversary-message:before,
  .aniversary-message:after {
    font-size: 1.5em;
    /* Adjust heart size for iPad */
  }
}

/* iPhone 11 (portrait) */
@media (max-width: 375px) {
  .delayed-fade-th{
    font-size:15px;
  }
  .anv-head {
    font-size: 20px;
  }

  .anv-body {
    font-size: 15px;
  }

  .aniversary-message {
    font-size: 1.1em;
    /* Adjust font size for iPhone 11 */
    padding: 10px;
    /* Adjust padding for iPhone 11 */
  }

  .aniversary-message:before,
  .aniversary-message:after {
    font-size: 1.2em;
    /* Adjust heart size for iPhone 11 */
  }
}
</style>
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Mitr">
</link>
