<script>
export default {
  name: 'ChatBoard',
  props: {
    messages: {
      type: Array,
      required: true
    }
  }
}
</script>

<template>
  <div class="chat">
    <div class="msg-container">
      <div
        v-for="(message, index) in messages"
        :key="index"
        :class="message.side == 'left' ? 'text-start' : 'text-end'"
      >
        <span class="name">{{ message.name }}</span>
        <p class="msg-text" :style="{ backgroundColor: message.color }">
          {{ message.message }}
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.chat {
  margin: 20px;
  border: 1px solid;
  border-radius: 8px;
  background-color: #e4e2d0;

  height: 500px;
}

.msg-container {
  height: 100%;
  overflow-y: auto;
  padding: 1rem;
}

.name {
  font-size: 16px;
  color: #888;
  margin-bottom: 4px;
}

.msg-text {
  padding: 8px;
  border-radius: 12px;
  font-size: 14px;
}
</style>
