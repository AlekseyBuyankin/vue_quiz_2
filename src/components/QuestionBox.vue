<template>
  <div>
    <b-jumbotron>
      <template v-slot:lead>
        Questions
      </template>

      <hr class="my-4" />

      <b-list-group>
        <b-list-group-item>Answers</b-list-group-item>
        <b-list-group-item>Answers</b-list-group-item>
        <b-list-group-item>Answers</b-list-group-item>
        <b-list-group-item>Answers</b-list-group-item>
      </b-list-group>

      <hr class="my-4" />

      <b-button variant="primary" href="#">Submit</b-button>
      <b-button variant="success">Next</b-button>
    </b-jumbotron>
  </div>
</template>

<style scoped>
.jumbotron {
  padding: 2rem 2rem;
}

.btn {
  margin: 0 5px;
}

.list-group-item:hover {
  background: #eee;
  cursor: pointer;
}
</style>
