<template>
  <div class="main">
    <a class="link-wrapper" :href="{ imagelink1: isMobile }">
      <div
        class="image-container img1"
        @mouseover="mouseOver"
        @mouseleave="mouseLeave"
      >
        <div class="image-number image-number-1">
          <p>
            1
          </p>
        </div>
        <img :src="imagefile1" />
        <div :class="{ active: isActive }" class="image-description">
          {{ imagedescription1 }}
          <a href="imagelink1" v-show="uselink">View</a>
        </div>
      </div>
    </a>
    <div class="image-container img2">
      <div class="image-number image-number-2">
        <p>
          2
        </p>
      </div>
      <img :src="imagefile1" />
    </div>
    <div class="image-container img3">
      <div class="image-number image-number-3">
        <p>
          3
        </p>
      </div>
      <img :src="imagefile1" />
    </div>
    {{windowWidth}}
  </div>
</template>

<script>
export default {
  props: {
    imagefile1: String,
    imagefile2: String,
    imagefile3: String,
    imagelink1: String,
    imagelink2: String,
    imagelink3: String,
    imagedescription1: String,
    imagedescription2: String,
    imagedescription3: String,
    uselink: Boolean
  },
  data() {
    return {
      isActive: false,
      isMobile: false,
      windowWidth: 0
    };
  },
  methods: {
    mouseOver: function() {
      this.isActive = !this.isActive;
    },
    mouseLeave: function(){
      this.isActive = false
    }
  },
  mounted() {
    this.$nextTick(()=>[
      window.addEventListener('resize', this.onResize)
    ])
  },
  beforeDestroy(){
    window.removeEventListener('resize', this.onResize)
  },
  onResize(){
    this.windowWidth = window.innerWidth
  }
};
</script>

<style scoped>
.main {
  display: flex;
  width: 100%;
}

.link-wrapper {
  display: flex;
  text-decoration: none;
  color: rgb(6, 0, 34);
}

.image-container {
  margin: auto;
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
  box-shadow: 0px 0px 10px #4b4b4b57;
}

.img1 img,
.img2 img,
.img3 img {
  max-height: 150px;
}

.img1::before {
  content: " ";
  position: fixed;
  background: rgba(228, 228, 228, 0.178);
  width: 150px;
  height: 280px;
  z-index: 200;
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

.image-description {
  display: none;
  filter: opacity(0);
  transition: 200ms;
}

.active {
  display: flex;
  flex-direction: column;
  text-align: center;
  filter: opacity(1);
  max-width: 120px;
  transition: 200ms;
}

@media (max-width: 700px) {
  .link-wrapper {
    display: none;
  }

  .main {
    flex-direction: column;
  }
  .img1 {
    transform: rotate(-10deg) translate(0px, 0px);
    transition: 200ms;
  }
  .img1:hover {
    transform: rotate(0deg) translate(0px, 0px) scale(1.5, 1.5);
  }
  .img2 {
    transform: rotate(10deg) translate(0px, 0px);
    transition: 200ms;
  }
  .img2:hover {
    transform: rotate(0deg) translate(0px, 0px) scale(1.5, 1.5);
  }
  .img3 {
    transform: rotate(20deg) translate(0px, 0px);
    transition: 200ms;
  }
  .img3:hover {
    transform: rotate(0deg) translate(0px, 0px) scale(1.5, 1.5);
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
