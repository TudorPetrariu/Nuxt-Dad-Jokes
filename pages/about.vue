<template>
  <div class="class">
    <ul>
      <h1>{{ title }}</h1>
      <li>What a ride</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "Learning Rebasig and amending commits",
    };
  },
  head() {
    return {
      title: "About dad JOkes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "best place for dad jokes",
        },
      ],
    };
  },
};
</script>

<style></style>
