<script setup lang="ts">
import { InputText } from "primevue";
import InputGroup from "primevue/inputgroup";
import InputGroupAddon from "primevue/inputgroupaddon";
import FloatLabel from "primevue/floatlabel";
import Button from "primevue/button";

import { computed, ref } from "vue";

const username = ref<string>("");
const password = ref<string>("");
const isLoginDisabled = computed(() => !username.value || !password.value);
</script>
<template>
  <div class="flex flex-column row-gap-5">
    <InputGroup>
      <InputGroupAddon>
        <i class="pi pi-user"></i>
      </InputGroupAddon>
      <FloatLabel>
        <InputText id="username" v-model="username" />
        <label for="username">Username</label>
      </FloatLabel>
    </InputGroup>
    <InputGroup>
      <InputGroupAddon>
        <i class="pi pi-lock"></i>
      </InputGroupAddon>
      <FloatLabel>
        <InputText type="password" id="password" v-model="password" />
        <label for="password">Password</label>
      </FloatLabel>
    </InputGroup>

    <Button label="Submit" :disabled="isLoginDisabled" />
  </div>
</template>
<style></style>
