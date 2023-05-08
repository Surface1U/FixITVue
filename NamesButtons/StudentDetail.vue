<template>
    <v-container>
    <v-card>
        <v-card-text>
        <div class="d-flex flex-column align-center">
          <v-img :src="studentImageUrl" height="200"></v-img>
          <p>Selected student: {{ studentName }}</p>
        </div>
      </v-card-text>
    </v-card>
      <v-btn icon href="https://vk.com/">
      <v-icon size="24">mdi-vk</v-icon>
    </v-btn>
    <v-btn icon href="https://github.com/">
      <v-icon size="24">mdi-github</v-icon>
    </v-btn>
    </v-container>



  </template>



  <script>
  export default {
    props: ['code'],
    computed: {
      studentName() {
        // Здесь можно получить данные о студенте из хранилища Vuex или из API
        const student = this.$store.state.student.students.get(this.code);
        return student ? student.fullName : 'Unknown student';
      },
      studentImageUrl() {
      const student = this.$store.state.student.students.get(this.code);
      return student && student.imageUrl ? student.imageUrl : 'https://via.placeholder.com/200x200?text=No+Image';
    }
    }
  };
  </script>
