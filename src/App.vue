<script setup lang="ts">
import { ref } from "vue";

const modalRef = ref<HTMLDialogElement>();

function popModal() {
  if (modalRef.value) {
    modalRef.value.showModal();
  }
}
function closeModal() {
  if (modalRef.value) {
    modalRef.value.close();
  }
}
</script>

<template>
  <main class="h-dvh w-full flex flex-col justify-center items-center">
    <button @click="popModal" class="border border-slate-500 px-4 py-1.5">
      Open Modal
    </button>
  </main>

  <dialog
    class="p-8 dark:bg-gray-800 bg-white dark:text-white text-black relative md:w-7/12 w-full backdrop:bg-black/60 mx-auto top-[50%] translate-y-[-50%] rounded-2xl duration-300 animate-in"
    ref="modalRef"
  >
    <div
      class="flex flex-col justify-center items-center min-h-[60dvh] max-h-[90vh]"
    >
      <h1 class="text-center">Hello world</h1>
    </div>

    <button
      class="absolute top-3 right-3 text-red-700 border border-red-700 px-3 py-0.5"
      @click="closeModal"
    >
      Close Modal
    </button>
  </dialog>
</template>

<style scoped></style>
