<template>
  <div>
    <ul>
      <li v-for="student in students" :key="student.code">
        {{ student.fullName }} ({{ student.code }})
      </li>
    </ul>
  </div>
</template>


  <script>

// import { mapActions } from 'vuex';
// import { mapGetters } from 'vuex';

export default {
  name: 'StoryAboutMy-Day',

  computed: {
    students() {
      return Array.from(this.$store.state.student.students.values())
    }

  }
}


  </script>
