<template>
   <div>
       <UploaderForm
               @chosen="handleFilesChosen"
       />
       <UploaderFile
        v-for="(upload, index) in uploads"
        :key="index"
        :upload="upload"
       />
   </div>
</template>

<script>
    import UploaderForm from '@/uploader/components/UploaderForm'
    import UploaderFile from '@/uploader/components/UploaderFile'

    export default {
        components: {
            UploaderForm,
            UploaderFile
        },

        data () {
            return {
                uploads: []
            }
        },

        methods: {
            handleFilesChosen (files) {
                this.uploads.push(...Array.from(files).map((file) => {
                    return {
                        file
                    }
                }))
            }
        }
    }
</script>