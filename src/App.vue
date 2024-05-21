<template>
  <div>
    <Navbar />
    <div class="container mt-4">
      <div class="main-content">
        <Sidebar />
        <div class="content">
          <Carousel />
          <div class="cards-container mt-4">
            <Card
              v-for="product in products"
              :key="product.id"
              :title="product.name"
              :description="product.description"
              :image="product.image"
            />
          </div>
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Carousel from './components/Carousel.vue';
import Card from './components/Card.vue';
import Footer from './components/Footer.vue';
import Sidebar from './components/Sidebar.vue';  // Import Sidebar

export default {
  name: 'App',
  components: {
    Navbar,
    Carousel,
    Card,
    Footer,
    Sidebar  // Register Sidebar
  },
  data() {
    return {
      products: [
        { id: 1, name: 'GG small tote bag', description: '$ 1,890 ', image: 'https://media.gucci.com/style/White_Center_0_0_250x170/1659457845/659983_92TCG_8563_001_078_0000_Light-GG-small-tote-bag.jpg' },
        { id: 2, name: 'Rectangular frame sunglasses', description: '$ 495 ', image: 'https://media.gucci.com/style/White_Center_0_0_250x170/1705339937/791813_J0740_2382_001_100_0000_Light-Rectangular-frame-sunglasses.jpg' },
        { id: 3, name: 'Cotton jersey T-shirt with embroidery', description: '$ 650 ', image: 'https://media.gucci.com/style/White_Center_0_0_250x170/1709566256/756596_XJFV8_4930_001_100_0000_Light-Cotton-jersey-T-shirt-with-embroidery.jpg' },
        { id: 4, name: 'Gucci print felted cotton jersey sweatshirt', description: '$ 1,200 ', image: 'https://media.gucci.com/style/White_Center_0_0_250x170/1713167199/789582_XJGLM_1082_001_100_0000_Light-Gucci-print-felted-cotton-jersey-sweatshirt.jpg' },
        { id: 5, name: 'Gucci Interlocking G print cotton T-shirt', description: '$ 590 ', image: 'https://media.gucci.com/style/White_Center_0_0_250x170/1715237106/788093_XJGL3_9669_001_100_0000_Light-Gucci-Interlocking-G-print-cotton-T-shirt.jpg' },
        { id: 7, name: 'GG technical jersey shorts with Web', description: '$ 1,250 ', image: 'https://media.gucci.com/style/White_Center_0_0_250x170/1713167193/789195_XJGLE_2270_001_100_0000_Light-GG-technical-jersey-shorts-with-Web.jpg' }
        // Add more products as needed
      ]
    };
  }
};
</script>

<style>
body {
  background-color: rgb(26, 7, 7);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.main-content {
  display: flex;
}

.content {
  flex: 1;
}

.container::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('https://www.hdwallpapers.in/download/gucci_word_surrounded_by_butterfly_and_flowers_hd_gucci-HD.jpg');
  background-size: cover;
  background-position: center;
  filter: blur(10px);
  z-index: -1;
}

.cards-container {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  justify-content: center;
}

.card {
  width: 300px;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 10px;
  background-color: #fff;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.card img {
  width: 100%;
  border-radius: 8px;
}

.card h2 {
  font-size: 24px;
  margin-bottom: 10px;
}

.card p {
  font-size: 18px;
  color: #666;
}
</style>
