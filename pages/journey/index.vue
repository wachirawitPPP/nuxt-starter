<template>
  <div>
    <instragramPost
      avatarSrc="/user.jpg"
      username="Memmories"
      imageSrc="/firstDate.jpg"
      caption="Fisrt date. ❤️"
      location="Klang Plaza ,Nakhonratchasima Thailand"
      date="12 March 2022"
    />
    <instragramPost
      avatarSrc="/user.jpg"
      username="Memmories"
      imageSrc="/firstDate2.jpg"
      caption="First met. 💖"
      location="Klang Plaza ,Nakhonratchasima Thailand"
      date="12 March 2022"
    />
    <instragramPost
      avatarSrc="/user.jpg"
      username="Memmories"
      imageSrc="/nan18.jpg"
      caption="First cake.🎂"
      location="Home ,Thailand"
      date="31 March 2022"
    />
    <instragramPost
      avatarSrc="/user.jpg"
      username="Memmories"
      imageSrc="/holdHand.jpg"
      caption="🧑🏻‍🤝‍👩🏼🧑🏻‍🤝‍👩🏼🧑🏻‍🤝‍👩🏼🧑🏻‍🤝‍👩🏼🧑🏻‍🤝‍👩🏼"
      location="Nakhonratchasima,Thailand"
      date="22 May 2022"
    />
  </div>
</template>

<script>
import InstragramPost from '~/components/instragramPost.vue'

export default {
  components: {
    InstragramPost
  },
  props:{
    avatarSrc:{
      type: String,
      default:"/public/cat.jpg"
    }
  }
}
</script>

<style>
body {
  background-color: #fafafa;
}
</style>
