<template>
  <li>
    <h2>{{ name }}</h2>
    <button @click="toggleDetails">Show Details</button>
    <ul v-if="detailsAreVisible">
      <li>
        <strong>Phone:</strong>
        {{ PhoneNumber }}
      </li>
      <li>
        <strong>Email:</strong>
        {{ emailAddress }}
      </li>
    </ul>
    <ul v-else>
      <p>Click on Show details see each friend info</p>
    </ul>
  </li>
</template>

<script>
export default {
  props:['name','PhoneNumber','emailAddress'],
  data() {
    return {
      detailsAreVisible: false,
      friend: {
        id: "manuel",
        name: "Manuel Lorenz",
        phone: "0123 45678 90",
        email: "manuel@localhost.com",
      },
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    }
  }
};
</script>