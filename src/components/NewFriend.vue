<template>
  <section>
    <form action="submit" @submit.prevent="submitData">
      <div>
        <label for="name">Name</label>
        <input type="text" v-model="newFriend.name" placeholder="Name" />
      </div>

      <div>
        <label for="email">Email</label>
        <input
          type="email"
          v-model="newFriend.emailAddress"
          placeholder="Email"
        />
      </div>
      <div>
        <label for="phone">Phone</label>
        <input type="tel" v-model="newFriend.phoneNumber" placeholder="Phone" />
      </div>
      <div><button>Submit</button></div>
    </form>
  </section>
</template>

<script>
export default {
  emits: ["add-contact"],
  data() {
    return {
      newFriend: {
        id: "",
        name: "",
        emailAddress: "",
        phoneNumber: "",
      },
    };
  },
  methods: {
    submitData() {
      this.$emit("add-contact", this.newFriend);
    },
  },
};
</script>

