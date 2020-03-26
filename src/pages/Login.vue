im
<template>
  <q-page class="bg-light-blue-13">
    <div class="row">
      <q-card class = "fixed-center col-md-4 col-xs-12 bg-white">
        <q-card-section>
          <div class="text-h6 q-pb-md">
            Halaman Login
          </div>
          <q-form
              @reset="onReset"
              @submit="onSubmit"
              class="q-gutter-md "
            >
              <q-input
                filled
                v-model="username"
                label="Username"
                lazy-rules
                :rules="[ val => val && val.length > 0 || 'Insert Your Username']"
              />

              <q-input
                filled
                type="password"
                v-model="password"
                label="Password"
                lazy-rules
                :rules="[ val => val !== null && val.length > 0 || 'Insert Your Password']"
              />
              <center>
                <q-btn to="/register" label="create new account" color="primary" flat class="q-ml-sm" />
              </center>

              <div>
                <q-btn label="Submit" type="submit" color="primary"/>
                <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
              </div>
            </q-form>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>
<script>

export default {
  data () {
    return {
      username: null,
      password: null
    }
  },
  methods: {
    onReset () {
      this.username = null
      this.password = null
    },
    onSubmit () {
      if (this.username === 'ridho' && this.password === '18421016') {
        this.$q.notify({
          type: 'positive',
          message: 'Berhasil Login'
        })
        this.$router.push('/home')
      } else {
        this.$q.notify({
          type: 'negative',
          message: 'Gagal Login'
        })
      }
    }
  }
}

</script>
