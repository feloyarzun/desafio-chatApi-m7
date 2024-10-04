<script>
export default {
  name: 'UserCard',
  data() {
    return {
      message: '',
      color: ''
    }
  },
  props: {
    user: {
      type: Object,
      required: true
    }
  },
  methods: {
    enviarMensaje() {
      this.$emit('enviar-mensaje', this.message, this.color, this.user.name.first, this.user.side)
      this.message = ''
    }
  },
  emits: ['enviar-mensaje']
}
</script>

<template>
  <div class="user-card card" style="width: 18rem">
    <img :src="user.picture.large" class="mt-3" />
    <div class="card-body text-center">
      <h5 class="card-title">{{ user.name.first }} {{ user.name.last }}</h5>
      <div class="form-group">
        <input v-model="color" type="color" class="form-control" />
      </div>
      <div class="form-group">
        <textarea
          v-model="message"
          class="form-control mt-2"
          rows="3"
          placeholder="Escribe tu mensaje"
        ></textarea>
      </div>

      <button @click="enviarMensaje" class="btn btn-primary mt-3">Enviar</button>
    </div>
  </div>
</template>

<style scoped>
.user-card {
  border-radius: 8px;
  border: solid 1px;
}
</style>
