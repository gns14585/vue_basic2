<template>
  <div class="modal" v-if="isModal">
    <div class="inner">
      <h3>{{ data[selectedMovie].title }}</h3>
      <p>영화 상세정보</p>
      <!--    자식컴포넌트에서 클릭 이벤트의 값을 변경할 수 없으니 부모컴포넌트로 값을 보내서 부모컴포넌트에서 처리하기  -->
      <!--    emit 은 자식컴포넌트에서 부모컴포넌트로 이동. $달러표시 closeModal은 보낼 이벤트이름 작명해야함  -->
      <!--    그리고 그 이벤트명을 부모에서 받아서 처리해야함 받을땐 @골뱅이로 표시  -->
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalComponent",
  props: {
    data: Array,
    isModal: Boolean,
    selectedMovie: Number,
  },
};
</script>

<style></style>
