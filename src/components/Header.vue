<template>
  <div>
    <b-nav>
      <b-nav-item disabled>Quiz</b-nav-item>
      <b-nav-item disabled
        >Total {{ num_current + 1 }}/{{ num_total + 1 }}
      </b-nav-item>
      <b-nav-item disabled>
        Counter {{ num_correct }}/{{ num_total + 1 }}
      </b-nav-item>
      <b-button @click="reset" variant="reset">Reset</b-button>
    </b-nav>
  </div>
</template>

<script>
export default {
  props: {
    num_total: null,
    num_current: null,
    num_correct: null,
    reset: Function
  }
};
</script>
