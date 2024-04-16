<template>
  <div class="event" :class="{ show: isOpen }">
    <p>{{ text }}</p>
    <button @click="isOpen = false">X</button>
  </div>
</template>

<script>
export default {
  name: "EventComponent",
  props: {
    text: String,
  },
  data() {
    return {
      isOpen: true,
    };
  },
};
</script>

<style>
.event {
  position: relative;
  background: #444;
  color: #ffffff;
  padding: 10px 20px;
  text-align: center;
  font-size: small;
  display: none;
}

.show {
  display: block;
}

.event p {
  margin: 0;
}

.event button {
  margin: 0;
  right: 20px;
  top: 8px;
  position: absolute;
}
</style>
