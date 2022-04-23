<template>
  <div v-if="student.name">

    <div class="alert alert-secondary" v-if="student.present">
      Welcome, {{ student.name }}
    </div>

    <div class="alert alert-success" v-else>
      Goodbye, {{ student.name }}. See you later!
    </div>

  </div>
</template>

<script>
export default {
  name: "StudentMessage.vue",
  props: {
    student: Object
  }
}
</script>

<style scoped>

</style>