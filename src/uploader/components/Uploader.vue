<template>
  <div>
    <UploaderForm @chosen="handleFilesChosen" />
    {{ options }}
    <UploaderFile
      :endpoint="determineEndpointFor(upload.file.type)"
      :baseURL="options.baseURL"
      v-for="(upload, index) in uploads"
      :key="index"
      :upload="upload"
    />
  </div>
</template>

<script>
import UploaderForm from "@/uploader/components/UploaderForm";
import UploaderFile from "@/uploader/components/UploaderFile";
import options from "@/uploader/options";
import get from "lodash.get"

export default {
  components: {
    UploaderForm,
    UploaderFile
  },

  props: {
    options: {
      required: false,
      type: Object,
      default: () => options
    },
    handlers: {
      required: true,
      type: Object
    }
  },

  data() {
    return {
      uploads: []
    };
  },

  methods: {
    determineEndpointFor (fileType) {
      return get(this.handlers[fileType], 'endpoint', null);
    },
    handleFilesChosen(files) {
      this.uploads.push(
        ...Array.from(files).map(file => {
          return {
            file
          };
        })
      );
    }
  }
};
</script>
