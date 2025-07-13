<template>
  <div class="login-section">
    <form>
      <!-- Email input -->
      <MDBInput
        type="email"
        label="Email address"
        id="form1Email"
        v-model="form1Email"
        wrapperClass="mb-4"
      />
      <!-- Password input -->
      <MDBInput
        type="password"
        label="Password"
        id="form1Password"
        v-model="form1Password"
        wrapperClass="mb-4"
      />
      <!-- 2 column grid layout for inline styling -->
      <MDBRow class="mb-4">
        <MDBCol class="d-flex justify-content-center">
          <!-- Checkbox -->
          <MDBCheckbox
            label="Remember me"
            id="form1LoginCheck"
            v-model="form1LoginCheck"
            wrapperClass="mb-3 mb-md-0"
          />
        </MDBCol>
        <MDBCol>
          <!-- Simple link -->
          <a href="#!">Forgot password?</a>
        </MDBCol>
      </MDBRow>
      <!-- Submit button -->
      <MDBBtn color="primary" type="button" block @click="onSubmit"> Sign in </MDBBtn>
    </form>
  </div>
</template>

<script setup>
import { MDBRow, MDBCol, MDBInput, MDBCheckbox, MDBBtn } from 'mdb-vue-ui-kit'
import { ref } from 'vue'

const emit = defineEmits(['onSubmit'])

const form1Email = ref('')
const form1Password = ref('')
const form1LoginCheck = ref(true)

function onSubmit() {
  emit('onSubmit')
  console.log('in login sevtion')
}
</script>

<style scoped>
.login-section {
  width: 300px;
}
</style>
