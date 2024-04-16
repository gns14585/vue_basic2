<template>
  <Navbar />
  <Event :text="text" />
  <Movies
    :data="data"
    @openModal="
      isModal = true;
      selectedMovie = $event;
    "
    @increseLike="increseLike($event)"
  />

  <Modal
    :data="data"
    :isModal="isModal"
    :selectedMovie="selectedMovie"
    @closeModal="isModal = false"
  />
  <!-- 자식컴포넌트에서 보낸 이벤트는 @골뱅이로 받기 -->
</template>

<script>
// moives에 있는 데이터를 import로 가져오기.
// movies는 단일 데이터이기 때문에 export default 로 사용
// 여러개의 데이터를 가져올땐 export {} 만 사용
import data from "./assets/movies";
import Navbar from "@/components/Navbar.vue";
import Modal from "@/components/Modal.vue";
import Event from "@/components/Event.vue";
import Movies from "@/components/Movies.vue";

export default {
  name: "App",
  data() {
    return {
      isModal: false,
      data: data,
      selectedMovie: 0,
      text: "NEPLIX 강렬한 운명의 드라마, 경기크리처!!!",
    };
  },
  methods: {
    increseLike(i) {
      this.data[i].like += 1;
    },
  },
  components: {
    Navbar: Navbar,
    Event: Event,
    Modal: Modal,
    Movies: Movies,
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
}

body {
  max-width: 768px;
  margin: 0 auto;
  padding: 20px;
}

h1,
h2,
h3 {
  margin-bottom: 1rem;
}

p {
  margin-bottom: 0.5rem;
}

button {
  margin-right: 10px;
  margin-top: 1rem;
}

.item {
  width: 100%;
  border: 1px solid #ccc;
  display: flex;
  margin-bottom: 20px;
  padding: 1rem;
}

.item figure {
  width: 30%;
  margin-right: 1rem;
}

.item img {
  width: 100%;
}

.item .info {
  width: 100%;
}

.modal {
  background: rgba(0, 0, 0, 0.7);
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal .inner {
  background: #fff;
  width: 80%;
  padding: 20px;
  border-radius: 10px;
}
</style>
