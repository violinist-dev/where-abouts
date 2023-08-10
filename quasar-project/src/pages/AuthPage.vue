<template>
  <q-page padding>
    
    <form @submit.prevent.stop="onSubmit">
      <div class="row flex items-center justify-center h-screen">
      
        <q-card flat bordered class="col-md-4 col-12">
          <q-card-section>
            <div class="text-h5">Login</div>
          </q-card-section>

          <q-card-section>
            <q-input rounded dense outlined v-model="formDetails.email" label="Username" lazy-rules :rules="nameRules" ref="nameRef" />
            <q-input rounded dense outlined v-model="formDetails.password" label="Password" :type="isPwd ? 'password' : 'text'" :rules="nameRules" ref="emailRef">
              <template v-slot:append>
                <q-icon :name="isPwd ? 'visibility_off' : 'visibility'" class="cursor-pointer" @click="isPwd = !isPwd" />
              </template>
            </q-input>
          </q-card-section> 

          <q-card-actions vertical>
            <q-btn unelevated type="submit" color="primary">Login</q-btn>
          </q-card-actions>
        </q-card>
        
      </div>

    </form>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'
import { useStoreAuthentication } from 'stores/storeAuthentication'

const store = useStoreAuthentication()

const isPwd = ref(true)

const nameRef = ref(null)
const emailRef = ref(null)
const nameRules = [val => (val && val.length > 0) || 'Please type something']

// data
const formDetails = ref({
  email: '',
  password: '',
})

//functions
function onSubmit() {
  nameRef.value.validate()
  emailRef.value.validate()

  if (nameRef.value.hasError || emailRef.value.hasError) {
    // form has error
  } else {
    store.loginUser(formDetails.value.email, formDetails.value.password)
  }
}
</script>
