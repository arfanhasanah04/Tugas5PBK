<template>
  <div class="card">
    <div class="image-container">
      <img :src="image" alt="Card image" class="card-image" />
    </div>
    <div class="card-content">
      <h2 class="cake-title">{{ title }}</h2>
      <p class="cake-price">{{ description }}</p>
      <button class="buy-button">Buy Now</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    title: String,
    description: String,
    image: String,
  },
};
</script>

<style>
.card {
  border: 1px solid #ddd;
  border-radius: 8px;
  overflow: hidden;
  width: 300px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.image-container {
  width: 100%;
  height: 200px; /* Set the desired image height */
  overflow: hidden;
}

.card-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.card-content {
  padding: 16px;
}

.cake-title {
  font-family: "Arial", sans-serif;
  font-size: 24px;
  color: #333; /* Example title color */
}

.cake-price {
  font-family: "Courier New", Courier, monospace;
  font-size: 20px;
  color: #ff9900; /* Example price color */
}

.buy-button {
  display: block;
  width: 100%;
  padding: 8px 16px;
  margin-top: 8px;
  font-family: "Arial", sans-serif;
  font-size: 16px;
  color: #fff;
  background-color: #010101; /* Example button color */
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.buy-button:hover {
  background-color: #0056b3; /* Darker button color on hover */
}
</style>
