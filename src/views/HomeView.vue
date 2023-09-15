<script setup>
document.body.classList.add('page-a-body');
</script>

<template>
  <section>
  <div id="carouselContain" class="carousel slide" style="margin-top: 100px;">
    <div class="carousel-indicators" >
      <button type="button" data-bs-target="#carousel" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
      <button type="button" data-bs-target="#carousel" data-bs-slide-to="1" aria-label="Slide 2"></button>
      <button type="button" data-bs-target="#carousel" data-bs-slide-to="2" aria-label="Slide 3"></button>
      <button type="button" data-bs-target="#carousel" data-bs-slide-to="3" aria-label="Slide 4"></button>
      <button type="button" data-bs-target="#carousel" data-bs-slide-to="4" aria-label="Slide 5"></button>
      <button type="button" data-bs-target="#carousel" data-bs-slide-to="5" aria-label="Slide 6"></button>
      <button type="button" data-bs-target="#carousel" data-bs-slide-to="6" aria-label="Slide 7"></button>
      <button type="button" data-bs-target="#carousel" data-bs-slide-to="7" aria-label="Slide 8"></button>
    </div>
    <div id="carouselControl" class="carousel slide" data-bs-ride="carousel">
    <div class="carousel-inner">
      <div class="carousel-item active" data-bs-interval="10000">
        <img src="src/assets/tahchang.jpg" class="d-block w-100" alt="...">
      </div>
      <div class="carousel-item" data-bs-interval="2000">
        <img src="src/assets/goodviews.jpg" class="d-block w-100" alt="...">
      </div>
      <div class="carousel-item">
        <img src="src/assets/riverside.jpg" class="d-block w-100" alt="...">
      </div>
      <div class="carousel-item">
        <img src="src/assets/warmup.jpg" class="d-block w-100" alt="...">
      </div>
      <div class="carousel-item">
        <img src="src/assets/thaynimman.jpg" class="d-block w-100" alt="...">
      </div>
      <div class="carousel-item">
        <img src="src/assets/lism.jpg" class="d-block w-100" alt="...">
      </div>
      <div class="carousel-item">
        <img src="src/assets/beerlab.jpg" class="d-block w-100" alt="...">
      </div>
      <div class="carousel-item">
        <img src="src/assets/tamma.jpg" class="d-block w-100" alt="...">
      </div>
    </div>
    <button class="carousel-control-prev" type="button" data-bs-target="#carouselControl" data-bs-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </button>
    <button class="carousel-control-next" type="button" data-bs-target="#carouselControl" data-bs-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </button>
  </div>
</div>
</section>
</template>

<style>

* {
  margin: 0;
  padding: 0;
}

.d-block {
  height: 90vh;
}

.carousel {
  margin-bottom: 2rem;
  margin-top: 2rem;
}


</style>
