<template>
  <v-container>
    <v-flex>
      <v-form v-model="valid" v-on:submit="handleSubmit($event)">
        <v-text-field
          v-model="login.user"
          :rules="login.userRules"
          label="Usuário"
          append-icon="fa-user"
          outline
          required
        ></v-text-field>
        <v-text-field
          v-model="login.password"
          :rules="login.passwordRules"
          label="Senha"
          type="password"
          append-icon="fa-key"
          required
          outline
        ></v-text-field>
        <v-btn depressed large block color="primary" dark class="mb-4">Entrar</v-btn>
        <v-btn outline block color="secundary" >Cadastrar</v-btn>
      </v-form>
    </v-flex>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      valid: false,
      login: {
        user: null,
        userRules: [
          v => !!v || 'Faltou escrever o seu Usuário'
        ],
        password: null,
        passwordRules: [
          v => !!v || 'Faltou digitar a sua Senha',
          v => v !== null && v.length <= 8 || 'A senha possui pelo menos 8 caracteres'
        ]
      }
    }),
    methods: {
      handleSubmit: function (e) {
        e.preventDefault()
        // Auth
        /*
        this.$auth.login({
          params: {auth: this.login},
          success: function () {
            console.log('Usuário logado com sucesso.')
          },
          error: function () {
            console.log('Usuário e/ou senha inválidos.')
          },
          rememberMe: true,
          redirect: '/cadastro'
        })
        */
      }
    }
  }
</script>

<style>

</style>
