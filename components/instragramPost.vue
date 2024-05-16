<template>
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-lg-6 col-md-8 col-sm-10">
          <div class="card m-3 p-2">
            <div class="card-header d-flex align-items-center">
              <img :src="avatarSrc" alt="User avatar" class="rounded-circle me-2" width="40" height="40">
              <div class="user-info">
                <span>{{ username }}</span>
                <div class="location">
                  <span>{{ postDate }}</span>
                  <span>{{ location }}</span>
                </div>
              </div>
            </div>
            <div class="card-image" @click="handleClick">
              <img :src="imageSrc" alt="Post image" class="img-fluid">
            </div>
            <div class="card-body">
              <div class="d-flex justify-content-start mb-2 icons">
                <i :class="liked ? 'bi bi-heart-fill text-danger me-2' : 'bi bi-heart'" @click="toggleLike"></i>
                <i class="bi bi-chat me-2"></i>
              </div>
              <p class="card-text">{{ caption }}</p>
              <p class="date-post">{{date}}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
<script>
export default {
    props: {
        avatarSrc: {
            type: String,
            default: "/public/cat.jpg"
        },
        username: {
            type: String,
            default: 'username'
        },
        imageSrc: {
            type: String,
            default: '/public/cat.jpg'
        },
        caption: {
            type: String,
            default: 'asdas'
        },
        location: {
            type: String,
            default: 'Somewhere' // Example location
        },
        date: {
            type: String,
            default: '00/00/0000' // Example location
        },
    },
        
    
    data() {
        return {
            liked: false,
            lastTap: 0
        };
    },
    methods: {
        toggleLike() {
            const currentTime = new Date().getTime();
            const tapLength = currentTime - this.lastTap;
            this.lastTap = currentTime;

            if (tapLength < 300) { // Adjust this value based on your preference
                this.liked = !this.liked;
            }
        },
        handleClick() {
            this.toggleLike();
        }
    }
}
</script>

<style scoped>
.card {
    border: 1px solid #dbdbdb;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.card-header {
    background-color: white;
    border-bottom: 1px solid #dbdbdb;
    padding: 10px;
}

.card-body {
    padding: 10px 15px;
}

.card-body .icons {
    font-size: 1.25rem;
    cursor: pointer;
    color: #333;
}

.card-body .icons .bi {
    transition: color 0.2s ease-in-out;
}

.card-body .icons .bi:hover {
    color: #007bff;
}

.card-image img {
    width: 100%;
    height: auto;
    transition: transform 0.2s ease-in-out;
}

.card-image img:hover {
    transform: scale(1.02);
}

.card-text {
    margin: 0;
    color: #555;
    font-size: 1rem;
    line-height: 1.5;
}

@media (max-width: 576px) {

    /* Phones */
    .card {
        width: 100%;
        margin-left: 0 !important;
        margin-right: 0 !important;

    }
}

.icons .bi {
    margin-right: 10px;
    /* Adjust margin as needed */
}

.location {
   font-size: small;
   color: #007bff;
}
.date-post {
    font-size: 11px;
    font-style: italic;
    color: #555;
}
</style>