<template>
  <b-col cols="12" lg="8" class="mt-3">
    <b-card class="rounded gl-bg-white-10 shadow h-100">
      <template v-slot:header>
        <MCSubtitle class="text-center text-danger">
          Announcement
        </MCSubtitle>
      </template>
      <template v-slot:footer>
        <b-button class="d-inline float-left" @click="older()">
          Older
        </b-button>
        <b-button class="d-inline float-right" @click="newer()">
          Newer
        </b-button>
      </template>
      <b-row>
        <b-col>
          <Body v-if="status === 0" :message-id="messageId" :date="date" :content="content" :author="author" />
          <Body v-else-if="status === 1" message-id="-" date="Oh no!" content="For some reason, we can't load this announcement!" author="API" />
          <div v-else class="text-center">
            <b-spinner variant="light" />
          </div>
        </b-col>
      </b-row>
    </b-card>
  </b-col>
</template>

<script>
import MCSubtitle from '~/components/mc/mc-subtitle'
import Body from '~/components/index/start/announcement/body'

export default {
  components: {
    MCSubtitle,
    Body
  },
  data () {
    return {
      offset: 0,
      status: -1,
      messageId: 0,
      date: '',
      content: '',
      author: ''
    }
  },
  created () {
    this.fetchAnnouncement(this.offset)
  },
  methods: {
    newer () {
      this.status = -1
      let i = this.offset - 1
      if (i < 0) { i = 0 }
      this.fetchAnnouncement(i).then((res) => {
        if (res) {
          this.offset = i
        }
      })
    },
    older () {
      this.status = -1
      const i = this.offset + 1
      this.fetchAnnouncement(i).then((res) => {
        if (res) {
          this.offset = i
        }
      })
    },
    fetchAnnouncement (offset) {
      return this.$axios
        .$post(process.env.api, {
          action: 'read',
          target: 'announcement',
          offset
        })
        .then((res) => {
          const { status } = res
          this.status = status
          if (status === 0) {
            const { id, author, date, content } = res
            this.messageId = id
            this.author = author
            this.date = date.substr(0, 10)
            this.content = content
          }
          return true
        })
        .catch((reason) => {
          this.status = 1
          return false
        })
    }
  }
}
</script>

<style>
.scrollable {
  position: relative;
  height: 350px;
  overflow-y: scroll;
}
</style>
