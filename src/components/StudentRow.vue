<template>

  <tr v-bind:class=" { present: student.present, absent: !student.present } ">
    <td>{{ student.name }}</td>
    <td>{{ student.starID }}</td>
    <td>
      <input type="checkbox" v-bind:checked="student.present" v-on:change="arrivedOrLeft(student, $event.target.checked)">
    </td>
  </tr>

</template>

<script>
export default {
  name: "StudentRow.vue",
  props: {
    student: Object
  },
  methods: {
    arrivedOrLeft(student, present) {
      this.$emit('arrived-or-left', student, present)
    }
  }
}
</script>

<style scoped>

.present {
  color: chartreuse;
}

.absent {
  color: brown;
  font-weight: bold;
}

</style>