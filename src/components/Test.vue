<template>
  <div class="test">
    <input type="text" v-model="title" /> <br/>
    <h1>{{title}}</h1>
    <p v-if="showName">{{user.firstName}}</p>
    <ul>
        <li v-for="item in items">
            {{item.title}}
        </li>
    </ul>
    <button v-on:click="greet('hello world')">Say Greeting</button>
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit"/>
    <hr />
    <label>First Name:</label>
    <input type="text" v-model="user.firstName" />
    <label>Last Name:</label>
    <input type="text" v-model="user.lastName" />
    <h3>{{fullName}}</h3>
  </div>
</template>

<script>
  export default {
    name: 'test',
    data() {
      return {
        title: 'Hello World',
        user: {
          firstName: 'John',
          lastName: 'Doe'
        },
        showName: false,
        items: [
          {title: 'item one'},
          {title: 'item two'},
          {title: 'item three'}
        ]
      }
    },
    methods: {
      greet: function(greeting) {
        alert(greeting)
      },
      pressKey: function(e) {
        console.log(e.target.value)
      },
      enterHit: function() {
        console.log('you hit enter')
      }
    },
    computed: {
      fullName: function() {
        return this.user.firstName + ' ' + this.user.lastName;
      }
    }
  }
</script>

<style scoped>

</style>
