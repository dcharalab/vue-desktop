<template>
  <div
    class="flex items-center justify-center h-screen h-full w-full flex items-center justify-center"
  >
    <file-selector v-model="files">
      <dropzone v-slot="{ hovered }">
        <div
          class="pb-4 pt-6 block w-full rounded-lg border-4 border-dashed border-gray-400 transition-colors duration-150 flex flex-col justify-center items-center"
          :class="{ 'border-blue-200': hovered }"
        >
          <div
            class="m-1 bg-white rounded-lg border border-gray-200 w-96 text-gray-900"
          >
            <div
              class="px-6 py-2 border-b border-gray-200 w-full break-words"
              v-for="file in files"
              :key="file.name"
            >
              {{ file.name }}
            </div>
          </div>
          <div>
            <dialog-button
              class="m-1 bg-indigo-500 hover:bg-indigo-400 transition-colors duration-150 rounded text-white px-4 py-2"
            >
              Επιλογή Αρχείων...
            </dialog-button>
            <button
              class="m-1 bg-violet-500 hover:bg-violet-400 transition-colors duration-150 rounded text-white px-4 py-2"
            >
              Μεταμόρφωση
            </button>
          </div>
        </div>
      </dropzone>
    </file-selector>
  </div>
</template>
<script>
import { ref } from "vue";
import { FileSelector, Dropzone, DialogButton } from "vue3-file-selector";

export default {
  components: {
    FileSelector,
    Dropzone,
    DialogButton,
  },
  setup() {
    const files = ref([]);

    return {
      files,
    };
  },
};
</script>
