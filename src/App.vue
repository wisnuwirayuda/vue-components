<script>
import Person from "./components/Person.vue";
import Alert from "./components/Alert.vue";
import Alerts from "./components/Alerts.vue";

export default {
  components: {
    Person,
    Alert,
    Alerts
  },
  data: () => ({
    items: 3,
    show: false,
    alert: {
      message: "Message",
      types: ["success", "warning", "danger"],
    }
  })
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
     <Alert message="Alert Message" type="danger" :show="true" />
  </div>
</template>