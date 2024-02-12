<script setup>
import { ref, computed } from 'vue'

const pendingImage = 'https://gifdb.com/images/high/cute-love-bear-roses-ou7zho5oosxnpo6k.gif';
const yesImage = 'https://media.tenor.com/gUiu1zyxfzYAAAAi/bear-kiss-bear-kisses.gif';
const noText = ref('No')
const sheSaidYes = ref(false)
const fontSize = ref(1)

function yes() {
  sheSaidYes.value = true
}

function no() {
  sheSaidYes.value = false
  fontSize.value += 1.5
  noText.value = randomNoText()
}

function randomNoText() {
  const noTexts = [
    'No',
    "Are you sure?",
    "Really sure?",
    "Think again!",
    "Last chance!",
    "Surely not?",
    "You might regret this!",
    "Give it another thought!",
    "Are you absolutely certain?",
    "This could be a mistake!",
    "Have a heart!",
    "Don't be so cold!",
    "Change of heart?",
    "Wouldn't you reconsider?",
    "Is that your final answer?",
    "You're breaking my heart ;(",
    "Can we reconsider, love?",
    "Heart's second thought?",
    "One more chance, darling?",
    "Rethink for us?",
  ];

  return noTexts[Math.floor(Math.random() * noTexts.length)];
}

const fontSizeRem = computed(() => `${fontSize.value}rem`)
</script>

<template>
  <main class="w-dvh h-dvh grid place-items-center overflow-hidden">
    <div class="flex flex-col gap-6">
      <template v-if="sheSaidYes">
        <img :src="yesImage" class="h-[200px] w-auto object-cover rounded-lg" alt="yes" />
        <h1 class="text-center font-medium text-3xl">Huraaaaa!</h1>
      </template>

      <template v-else>
        <div class="mx-auto">
          <img :src="pendingImage" class="h-[200px] w-auto object-cover rounded-lg" alt="pending" />
        </div>
        <h1 class="text-center font-medium text-3xl">Will you be my Valentine?</h1>
        <div class="space-x-4 space-y-4 mx-auto">
          <button type="button" class="px-6 py-2 text-white bg-cyan-500 rounded-md hover:bg-cyan-600 transition"
            :style="{ fontSize: fontSizeRem }" @click="yes">
            Yes
          </button>
          <button type="button" class="px-6 py-2 text-white bg-rose-500 rounded-md" @click="no">
            {{ noText }}
          </button>
        </div>
      </template>
    </div>
  </main>
</template>