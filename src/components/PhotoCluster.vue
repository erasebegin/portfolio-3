<template>
  <div class="main">
    <div class="image-container img1">
      <div class="image-number image-number-1">
        <p>
          1
        </p>
      </div>
      <img :src="image1" />
    </div>
    <div class="image-container img2">
      <div class="image-number image-number-2">
        <p>
          2
        </p>
      </div>
      <img :src="image1" />
    </div>
    <div class="image-container img3">
      <div class="image-number image-number-3">
        <p>
          3
        </p>
      </div>
      <img :src="image1" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    image1: String,
    image2: String,
    image3: String,
    imagelink1: String,
    imagelink2: String,
    imagelink3: String
  }
};
</script>

<style scoped>
.main {
  display: flex;
  width: 100%;
}

.image-container {
  position: absolute;
  border: 1px solid black;
  padding: 1em;
  background: white;
  box-shadow: 1px 1px 5px #5a5a5a57;
}

.img1 {
  transform: rotate(-20deg) translate(60px, 70px);
  transition: 200ms;
}

.img1:hover {
  transform: rotate(-17deg) translate(60px, 70px) scale(1.1, 1.1);
}

.img2 {
  transform: rotate(10deg) translate(200px, 150px);
  transition: 200ms;
}

.img2:hover {
  transform: rotate(13deg) translate(200px, 150px) scale(1.1, 1.1);
}

.img3 {
  transform: rotate(20deg) translate(300px, 300px);
  transition: 200ms;
}

.img3:hover {
  transform: rotate(18deg) translate(300px, 300px) scale(1.1, 1.1);
}

.img1:hover,
.img2:hover,
.img3:hover {
  z-index: 100;
  transition: 200ms;
  box-shadow: 1px 1px 10px #4b4b4b57;
}

.img1 img,
.img2 img,
.img3 img {
  max-height: 150px;
}

.image-number {
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
  font-weight: 700;
  position: fixed;
  text-align: center;
  padding: 0.5em;
  height: 40px;
  width: 40px;
  background: rgba(255, 255, 255, 0.801);
  border: 3px solid rgba(24, 24, 24, 0.842);
  border-radius: 100%;
}

.image-number-1 {
  transform: translate(-20px, -20px);
}

.image-number-2 {
  transform: translate(190px, -20px);
}

.image-number-3 {
  transform: translate(-20px, -20px);
}

@media (max-width: 700px) {
  .img1 {
    transform: rotate(20deg) translate(250px, 50px);
    transition: 200ms;
  }
  .img1:hover {
    transform: rotate(5deg) translate(250px, 50px) scale(1.5, 1.5);
  }
  .img2 {
    transform: rotate(20deg) translate(200px, 250px);
    transition: 200ms;
  }
  .img2:hover {
    transform: rotate(5deg) translate(200px, 250px) scale(1.5, 1.5);
  }
  .img3 {
    transform: rotate(40deg) translate(400px, 50px);
    transition: 200ms;
  }
  .img3:hover {
    transform: rotate(30deg) translate(400px, 50px) scale(1.5, 1.5);
  }

  .img1 img,
  .img2 img,
  .img3 img {
    max-height: 100px;
  }

  .image-number-1 {
    transform: translate(-30px, -30px);
  }

  .image-number-2 {
    transform: translate(-30px, -30px);
  }

  .image-number-3 {
    transform: translate(-30px, -30px);
  }
}
</style>
