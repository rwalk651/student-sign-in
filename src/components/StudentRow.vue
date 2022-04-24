<template>

  <tr v-bind:class=" { present: student.present, absent: !student.present } ">
    <td>{{ student.name }}</td>
    <td>{{ student.starID }}</td>
    <td>
      <input type="checkbox" v-on:change="arrivedOrLeft(student, $event.target.checked)">
    </td>
    <td> <img v-show="edit" v-on:click="deleteStudent" src="@/assets/delete.png" alt=""></td>
  </tr>

</template>

<script>
export default {
  name: "StudentRow.vue",
  props: {
    student: Object,
    edit: Boolean
  },
  methods: {
    arrivedOrLeft(student, present) {
      this.$emit('arrived-or-left', student, present)
    },
    deleteStudent() {
      if (confirm(`Delete $(this.student.name?`)) {
        this.$emit('delete-student', this.student)
      }
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

img {
  height: 20px;
}

</style>