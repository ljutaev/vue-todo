<template>
  <v-layout class="app-layout">
    <v-flex xs12 sm6>
      <v-card>
        <v-card-title primary-title>
          <div>
            <h3 class="headline mb-0">Create Your Task</h3>
          </div>
        </v-card-title>
        <v-card-title>
          <v-text-field
            v-model="name"
            :counter="15"
            label="Task Name"
            @keydown.enter="add"
          ></v-text-field>
        </v-card-title>
        <v-card-actions>
          <v-spacer />
          <v-btn flat @click="add" color="orange">Add Task</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
    <v-flex xs12 sm6>
      <v-card>
        <v-card-title primary-title>
          <div>
            <h3 class="headline mb-0">Task List</h3>
          </div>

        </v-card-title>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  export default {
    data() {
      return {
        name: ''
      }
    },
    methods: {
      add() {
        this.$emit('taskAdded', { name: this.name }),
        console.log(this.name)
      }
    }
  }
</script>

<style>
  .app-layout{
    padding-top: 60px
  }
</style>
