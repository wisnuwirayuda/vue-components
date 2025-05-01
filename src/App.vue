<script>
import Person from "./components/Person.vue";
import Alert from "./components/Alert.vue";
import Alerts from "./components/Alerts.vue";
import LoginForm from "./components/auth/LoginForm.vue";
import BaseInput from "./components/BaseInput.vue";
import BaseButton from "./components/BaseButton.vue";
import Modal from "./components/Modal.vue";
import TodoList from "./components/TodoList.vue";

export default {
  components: {
    Person,
    Alert,
    Alerts,
    LoginForm,
    BaseInput,
    BaseButton,
    Modal,
    TodoList
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
    <!-- <Alert type="success" :show="show" @alert-close="show = false" v-slot="{ alertLink }">
      The Alert Message <a href="#" :class="alertLink">Alert Link</a>
    </Alert> -->

    <!-- <LoginForm @submit="handleSubmit" v-model:email.lowercase="email" v-model:password="password" /> -->
    
    <!-- <BaseInput v-model.lowercase="email" label="Email" type="email" /> -->
    <!-- <BaseButton text="Submit" theme="primary" @click="show = true" class="mt-3" id="button" /> -->
    <!-- {{ email }} - {{ password }} -->

    <!-- <Modal :show="true">
      VERSI KEDUA
      <template #header>The Modal Title</template>
      <template #default>
        <p>The Modal Body</p>
      </template>
      <template #footer>
        <button class="btn btn-primary">Save</button>
      </template>

      VERSI PERTAMA
      <template v-slot:header>The Modal Title</template>
      <template v-slot:default>
        <p>The Modal Body</p>
      </template>
      <template v-slot:footer>
        <button class="btn btn-primary">Save</button>
      </template>
    </Modal> -->

    <TodoList>
      <template #default="{ name }">
        <input type="checkbox" class="form-check-input me-1" />
        <label class="form-check-label">{{ name }}</label>

        <!-- <p class="mb-0 pb-2">{{ name }}</p>
        <button class="btn btn-sm btn-success">Done</button> -->
      </template>

      <template #footer="{ all, todo, done }">
        <div class="d-flex justify-content-between align-items-center">
          <span class="text-muted">All ({{ all }})</span>
          <span class="text-muted">Todo ({{ todo }})</span>
          <span class="text-muted">Done ({{ done }})</span>
        </div>
      </template>
    </TodoList>
  </div>
</template>