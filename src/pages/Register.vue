
<template>
  <q-page class="flex flex-center bg-light-blue-2">
    <div class="q-pa-md bg-grey-2" style="width: 400px ">
    <q-item-label header>Register Panel</q-item-label>
    <q-form
      @reset="onReset"
      @submit="onSubmit"
      class="q-gutter-md"
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
        v-model="nama"
        label="Name"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Insert Your Name']"
      />

      <q-input
        filled
        v-model="email"
        label="Email"
        lazy-rules
        :rules="[ val => val !== null && val.length > 0 || 'Insert Your Email']"
      />

      <q-input
        filled
        type="password"
        v-model="password"
        label="Password"
        lazy-rules
        :rules="[
        val => val !== null && val.length > 0 || 'Insert Your Password']"
      />

      <q-input
        filled
        type="password"
        v-model="repassword"
        label="Re-Type Password"
        lazy-rules
        :rules="[
        val => val !== null && val.length > 0 || 'Insert Your Password']"

      />
      <div>
        <q-btn label="Submit" type="submit" color="primary"/>
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>
    </div>
  </q-page>
</template>
<script>

export default {
  data () {
    return {
      username: null,
      password: null,
      repassword: null,
      nama: null,
      email: null
    }
  },
  methods: {
    onReset () {
      this.username = null
      this.password = null
      this.nama = null
      this.email = null
      this.repassword = null
    },
    onSubmit () {
      if (this.username !== null && this.password !== null) {
        this.$q.notify({
          type: 'positive',
          message: 'Berhasil Login'
        })
        this.$router.push('/')
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
