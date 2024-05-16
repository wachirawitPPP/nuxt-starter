<template>
  <div>
    <instragramPost
      avatarSrc="/user.jpg"
      username="Memmories"
      imageSrc="/firstDate.jpg"
      caption="Fisrt date ,First met. ❤️"
      location="Klang Plaza ,Nakhonratchasima Thailand"
    />
    <instragramPost
      avatarSrc="/user.jpg"
      username="Memmories"
      imageSrc="/firstDate.jpg"
      caption="Fisrt Date. ❤️"
      location="Klang Plaza ,Nakhonratchasima Thailand"
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
