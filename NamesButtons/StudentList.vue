<template>
  <v-container>
    <v-card>
      <v-card-title>Student List</v-card-title>
      <v-card-text>
        <v-list>
          <v-list-item v-for="student in students" :key="student.code" :to="{ name: 'student-detail', params: { code: student.code }}">
            <v-list-item-title>{{ student.fullName }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: 'StudentList',
  computed: {
    students() {
      return Array.from(this.$store.state.student.students.values())
    }
  }
}
</script>
