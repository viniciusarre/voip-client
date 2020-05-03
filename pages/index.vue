<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <div class="mt-4">
        <meeting-card
          :title="`Assistindo a palestra da Sala ${ auditoryNumber }`"
          src="https://www.youtube.com/embed/1wRzL4HNVsw?autoplay=1&controls=0&showinfo=0&showtitle=0"
        />
      </div>
      <div class="mt-12 d-flex flex-row">
        <user-avatar
          v-for="(user, index) in users"
          :key="user.name"
          :user="user"
          :color="colors[index]"
        />
      </div>
    </v-flex>
  </v-layout>
</template>

<script>
import MeetingCard from '@/components/MeetingCard'
import UserAvatar from '@/components/UserAvatar'
export default {
  components: {
    MeetingCard,
    UserAvatar
  },
  data () {
    return {
      auditoryNumber: 1,
      users: [
        {
          name: 'User 1',
          current: true
        },
        {
          name: 'User 2'
        },
        {
          name: 'User 3'
        },
        {
          name: 'User 4'
        },
        {
          name: 'User 5'
        },
        {
          name: 'User 6'
        }
      ],
      colors: [
        'red',
        'green',
        'purple',
        'blue',
        'orange',
        'pink'
      ]
    }
  }
}
</script>
