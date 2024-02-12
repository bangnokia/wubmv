<script setup>
const pendingImage = 'https://gifdb.com/images/high/cute-love-bear-roses-ou7zho5oosxnpo6k.gif';
const yesImage = 'https://gifdb.com/images/high/cute-love-bear-roses-ou7zho5oosxnpo6k.gif';
</script>

<template>
  <main class="w-dvh h-dvh grid place-items-center">
    <div class="flex flex-col">
      <img :src="pendingImage" class="h-[200px]" alt="pending" />
    </div>
  </main>
  <h1>this is the main page</h1>
</template>