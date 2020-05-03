<template>
  <span>

    <v-avatar
      :color="color"
      height="150"
      width="150"
      class=" mr-12"
    >
      <span
        v-if="user.current"
        class="white--text headline"
      >
        {{ "Você" }}
      </span>
      <span
        v-else
        class="white--text headline"
      >
        {{ nameInitials }}
      </span>
    </v-avatar>

  </span>
</template>

<script>
export default {
  props: {
    user: {
      type: Object,
      required: true
    },
    color: {
      type: String,
      default: 'red'
    }
  },
  computed: {
    nameInitials () {
      const split = this.user.name.split(' ')
      return `${split[0][0]}${split[1][0]}`
    }
  }
}
</script>

<style scoped>
    .is-selected {
        border: 10px solid;
        border-color: lightgray;
    }
</style>
