<template>
  <v-container style="max-width: 500px;">
      <form style="margin-top: 3rem;">
        <h2>비밀번호 변경</h2>
        <p>가입하신 이메일과 이름을 입력하세요.</p>
        <v-text-field
          v-model="email"
          label="E-mail"
          required
        ></v-text-field>
        <v-text-field
          v-model="name"
          label="Name"
          required
        ></v-text-field>
        <v-btn
          class="mb-3"
          @click="handleSubmit"
          fluid
        >
          비밀번호 찾기
        </v-btn>
        </form>
  </v-container>
</template>


<script>

export default {
  name: 'ForgotPasswordForm',
  data() {
    return {
      email: '',
      name: ''
    }
  },
  methods: {
    handleSubmit() {
      const{email, name} = this
      this.$emit('submit', { email, name })
    }
  }
}
</script>