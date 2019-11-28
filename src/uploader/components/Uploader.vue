<template>
    <UploaderForm
        @chosen="handleFilesChosen"
    />
</template>

<script>
    import UploaderForm from '@/uploader/components/UploaderForm';

    export default {
        components: {
            UploaderForm
        },

        methods: {
            handleFilesChosen (files) {
                console.log(files)
            }
        }
    }
</script>