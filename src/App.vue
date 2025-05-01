<script>
import Person from "./components/Person.vue";
import Alert from "./components/Alert.vue";
import Alerts from "./components/Alerts.vue";
import LoginForm from "./components/auth/LoginForm.vue";
import BaseInput from "./components/BaseInput.vue";
import BaseButton from "./components/BaseButton.vue";

export default {
  components: {
    Person,
    Alert,
    Alerts,
    LoginForm,
    BaseInput,
    BaseButton
  },
  data: () => ({
    items: 3,
    show: true,
    alert: {
      message: "Message",
      types: ["success", "warning", "danger"],
    },
    email: '',
    password: '',
    message: 'Alert Message'
  }),
  methods: {
    handleSubmit(email, password) {
      alert(email + ' ' + password);
    } 
  }
}
</script>

<template>
  <div class="container py-5">
    <!-- <Person :age="25" first-name="John" last-name="Doe" /> -->
    <!-- STATIS PROPS -->
    <!-- <Person age="25" first-name="Wisnu" last-name="Trenggono Wirayuda" /> -->
    <!-- <Alert message="Hi there" type="success" /> -->

    <!-- DYNAMIC PROPS -->
    <!-- <Alert :message="items + ' items has been removed'" type="success" :show="true" /> -->
    <!-- <Alerts :message="items + ' items has been removed'" type="success" :types="['success', 'warning', 'danger']" /> -->
    <!-- <Alerts v-bind="alert" /> -->
    <Alert type="danger" :show="show" @alert-close="show = false">
    </Alert>

    <!-- <LoginForm @submit="handleSubmit" v-model:email.lowercase="email" v-model:password="password" /> -->
    
    <!-- <BaseInput v-model.lowercase="email" label="Email" type="email" /> -->
    <!-- <BaseButton text="Submit" theme="primary" @click="show = true" class="mt-3" id="button" /> -->
    <!-- {{ email }} - {{ password }} -->
  </div>
</template>