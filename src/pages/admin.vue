<script setup lang="ts">

</script>

<template>
  <NuxtExample
      class="h-50"
      dir="advanced/use-cookie"
  >
    <template v-if="user">
      <h1 class="text-3xl mb-3">
        Welcome, {{ user.email }}! 👋
      </h1>
      <div>
        <UAlert
            title="Logged-In"
            color="primary"
            icon="i-heroicons-light-bulb"
        >
          <template #description>
            You have logged in <b>{{ logins }} times</b>!
          </template>
        </UAlert>
      </div>
      <div class="mt-3">
        <UButton
            color="warning"
            icon="i-heroicons-arrow-left"
            @click="logout"
        >
          Log out
        </UButton>
      </div>
    </template>
    <template v-else>
      <h1 class="text-3xl mb-3">
        Login
      </h1>
      <UInput
          v-model="email"
          class="w-100 m-auto"
          placeholder="Enter your name..."
          @keypress.enter="login()"
      />
      <div class="mt-3">
        <UButton
            icon="i-heroicons-user"
            :disabled="!emil"
            name="Log in"
            @click="login"
        >
          Log in
        </UButton>
      </div>
    </template>
  </NuxtExample>
</template>
