<template>
  <div class="result">
    <div class="title">You got sample result {{ totalCorrect }}!</div>
    <div class="desc">Enter a short description here about the result.</div>
  </div>
</template>

<script>
export default {
  props: {
    results: {
      type: Object,
    },
    totalCorrect: {
      type: Number,
    },
  },

  //   computed: {
  //     resultIndex() {
  //       let Index = 0;
  //           result.forEach((item,index) => {
  //         if(item.min<totalCorrect && item.max<=)
  //       });
  //     },
  //   },
};
</script>

<style lang="scss" scoped></style>
