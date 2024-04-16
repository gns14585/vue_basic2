<template>
  <div class="event">
    <p>{{ text }}</p>
    <button>X</button>
  </div>
</template>

<script>
export default {
  name: "EventComponent",
  props: {
    text: String,
  },
};
</script>

<style>
.event {
  background: #444;
  color: #ffffff;
  padding: 10px 20px;
  text-align: center;
  font-size: small;
  display: flex;
  justify-content: space-between;
  align-items: center;
  display: none;
}

.event p {
  margin: 0;
}

.event button {
  margin: 0;
}
</style>
