<template>
  <div class="carousel">
    <div v-for="(image, index) in images" :key="index" class="carousel-item" @click="openModal(image.url)">
      <img :src="image.url" :alt="image.alt" class="carousel-image" />
    </div>
    <div v-if="modalOpen" class="modal" @click="closeModal">
      <img :src="modalImageUrl" alt="Full-size Image" class="modal-image" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Carousel',
  data() {
    return {
      images: [
        { url: 'https://wallpapercave.com/wp/NZnU7lY.jpg' },
        { url: 'https://papers.co/wallpaper/papers.co-ht77-girl-kpop-jennie-gucci-snow-29-wallpaper.jpg' },
        { url: 'https://images.hdqwalls.com/wallpapers/ryan-gosling-gucci-photoshoot-5k-mq.jpg' }
      ],
      modalOpen: false,
      modalImageUrl: ''
    }
  },
  methods: {
    openModal(url) {
      this.modalOpen = true;
      this.modalImageUrl = url;
    },
    closeModal() {
      this.modalOpen = false;
    }
  }
}
</script>

<style>
.carousel {
  display: flex;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  padding: 10px;
  margin-bottom: 20px;
}

.carousel-item {
  scroll-snap-align: start;
  flex: none;
  width: 100%;
  margin-right: 10px;
  border-radius: 8px;
  overflow: hidden;
}

.carousel-image {
  width: 100%; /* Set the width to fill the entire container */
  height: auto; /* Automatically adjust the height to maintain aspect ratio */
  object-fit: cover; /* Cover the entire area of the container */
  border-radius: 8px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.carousel-item:hover .carousel-image {
  transform: scale(1.05);
}

.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-image {
  max-width: 90%;
  max-height: 90%;
  object-fit: contain;
}
</style>
