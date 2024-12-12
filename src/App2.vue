<script>
export default {
  data() {
    return {
      name: 'John Doe',
      status: true,
      tasks: ['task1', 'task2', 'task3'],
      link: 'https://google.com'
    }
  },
  methods: {
    toggleStatus() {
      if (this.status === 'active') {
        this.status = 'pending'
      }
      else if (this.status === 'pending') {
        this.status ='inactive'
      }
      else {
        this.status = 'active'
      }
    }
  }

}
</script>

<template>
  <h1>Hello {{ name }}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>
  <ul>
    <li v-for="task in tasks" :key="task">
      {{ task }}
    </li>
  </ul>
  <!-- <a v-bind:href="link">Click for google</a> -->
  <!-- this is fixed link, to make it dynamic dont use the v-bind  -->
  <a :href="link">Click for google</a>

  <br />
  <!-- <button v-on:click="toggleStatus">Change Status</button> -->
  <button @click="toggleStatus">Change Status</button>
</template>

//accessing the name after decalring in the script data is interpolation
//directives is the condition and u use it using the v-if
//v-for is used for looping
