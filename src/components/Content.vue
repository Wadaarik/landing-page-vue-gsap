<template>
  <div class="images">
    <div class="left img"></div>
    <div class="right img"></div>
  </div>

  <div class="hero-image">
    <div class="wrapper-img">
      <div class="box"></div>
      <div>
        <img class="image" :src="image"  alt="img two"/>
      </div>
    </div>
  </div>

  <div class="header"><p class="title">antidote</p></div>

  <div class="hero-container">
    <div class="sidebar-text">003</div>
    <div class="projects">projects</div>
    <div class="img-nav">
      <div class="prev">prev</div>
      <div class="next">next</div>
    </div>
  </div>
</template>

<script>
import img_two from '../assets/images/img-two.jpg';
import gsap from "gsap";

export default {
  name: "Content",
  data: function () {
    return {
      image: img_two
    }
  },
  mounted() {
    var textWrapper = document.querySelector(".title");
    textWrapper.innerHTML = textWrapper.textContent.replace(
        /\S/g,
        "<span class='letter'>$&</span>"
    );
    gsap.timeline().add({
      targets: ".title .letter",
      translateY: [100, 0],
      translateZ: 0,
      opacity: [0, 1],
      easing: "easeOutExpo",
      duration: 2000,
      delay: (el, i) => 4800 + 40 * i,
    });
    gsap.to(".box", 2.4, {
      y: "-100%",
      ease: "expo.easeInOut",
      delay: 1,
    });

    gsap.from("img", 4, {
      scale: "2",
      ease: "expo.easeInOut",
      delay: 0,
    });

    gsap.to(".wrapper-img", 2.4, {
      width: "400",
      height: "500",
      ease: "expo.easeInOut",
      delay: 3.6,
    });

    gsap.from(".img", 0.4, {
      opacity: 0,
      ease: "expo.easeInOut",
      delay: 3.4,
    });

    gsap.to(".left", 2, {
      x: "-250",
      rotation: -10,
      ease: "expo.easeInOut",
      delay: 3.8,
    });

    gsap.to(".right", 2, {
      x: "250",
      rotation: 10,
      ease: "expo.easeInOut",
      delay: 3.8,
    });

    gsap.staggerFrom(
        ".menu > div, .hero-container > div",
        2,
        {
          opacity: 0,
          y: 30,
          ease: "expo.easeInOut",
          delay: 4.2,
        },
        0.1
    );
  }
}
</script>

<style scoped>
.hero-image {
  position: absolute;
  top: 0;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.wrapper-img {
  position: absolute;
  overflow: hidden;
  position: relative;
  margin: 0 auto;
  width: 50%;
  height: 100vh;
}

img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.box {
  background: #bebeb8;
  opacity: 1;
  position: absolute;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  z-index: 2;
}

.images {
  position: absolute;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.img {
  position: absolute;
  top: 40%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 300px;
  height: 400px;
  background: black;
}

.left {
  background: url("../assets/images/img-one.jpg")
  no-repeat 50% 50%;
  background-size: cover;
}

.right {
  background: url("../assets/images/img-three.jpg")
  no-repeat 50% 50%;
  background-size: cover;
}

p {
  width: 100%;
  text-align: center;
  position: absolute;
  top: 45%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: red;
  font-family: "Voyage";
  font-size: 300px;
}

.title .letter {
  display: inline-block;
  line-height: 1em;
}


.sidebar-text {
  font-family: "Monument Extended";
  position: absolute;
  top: 20%;
  right: 0.4em;
  transform: translate(-50%, -50%);
  font-size: 40px;
  color: transparent;
  -webkit-text-stroke: 1px rgb(117, 113, 113);
}

.projects {
  position: absolute;
  bottom: 10%;
  left: 10%;
  transform: translate(-50%, -50%);
  text-transform: uppercase;
  font-family: "Monument Extended";

}

.img-nav {
  position: absolute;
  right: 10%;
  bottom: 13%;
  transform: translate(-50%, -50%);
  text-transform: uppercase;
  color: #000;
  font-family: "Monument Extended";

}

.next {
  position: relative;
  top: 40px;
  left: 80px;
  font-family: "Monument Extended";

}
</style>