<template>
  <v-app>
    <v-main>
      <v-container>
        <h1>To-Do List</h1>
        <v-card elevation="2" style="padding: 12px">
          <ListItem/>
        </v-card>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import ListItem from './components/ListItem';

export default {
  name: 'App',

  components: {
    ListItem,
  },

  data: () => ({
    //
  }),
};
</script>
