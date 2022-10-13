<template>
  <div>
    <file-selector v-model="files">
      <dropzone v-slot="{ hovered }">
        <div
          class="p-2 block h-screen w-full rounded-lg border-4 border-dashed border-gray-400 transition-colors duration-150 flex flex-col justify-center items-center"
          :class="{ 'border-blue-200': hovered }"
        >
          <div
            class="bg-white rounded-lg border border-gray-200 w-96 text-gray-900 w-full"
          >
            <div
              class="px-6 py-2 border-b border-gray-200 w-full"
              v-for="file in files"
              :key="file.name"
            >
              {{ file.name }}
            </div>
          </div>
          <dialog-button
            class="bg-indigo-500 hover:bg-indigo-400 transition-colors duration-150 rounded text-white px-4 py-2"
          >
            Επιλογή Αρχείων...
          </dialog-button>
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
