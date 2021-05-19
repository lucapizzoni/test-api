<template>
  <v-app>
    <v-main>
      <v-container>
        <h1>To-Do List</h1>
        <v-card elevation="2" style="padding: 12px">
          <v-checkbox
          v-for="(todo, i) in todos"
          :key="i"
          :model="todo.completed"
          :label="todo.title"
          ></v-checkbox>
          <!-- <v-list>
            <v-list-item
              v-for="(item, i) in items"
              :key="i"
            >
              <v-list-item-icon>
                <v-icon v-text="item.icon"></v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title v-text="item.text"></v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list> -->


          <!-- <v-list>
            <v-list-item>
              <v-list-item-content>
                <v-list-item-title>Single-line item</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
          <ListItem/> -->
        </v-card>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
// import ListItem from './components/ListItem';
import axios from 'axios'

export default {
  name: 'App',
  components: {
    // ListItem,
  },
  data() {
    return {
      todos: null
    }
  },
  created() {
    axios.get('https://my-json-server.typicode.com/lucapizzoni/test-api/todos')
    .then(response => {
      this.todos = response.data
    })
    .catch(error => {
      console.log(error)
    })
  }
};
</script>
