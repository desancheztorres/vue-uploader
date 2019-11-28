<template>
    <form
        enctype="multipart/form-data"
        novalidate
        class="bg-gray-200 border-gray-400 border-2 border-dashed rounded-lg p-10 flex items-center justify-center mb-6 relative"
    >
        <input
                type="file"
                multiple
                class="absolute opacity-0 w-full h-full top-0 left-0"
                @change="handleFilesChosen"
        >
        <div class="text-gray-700">
            Drop here to upload or <span class="text-blue-500">choose files</span>
        </div>
    </form>
</template>

<script>
    export default {
        methods: {
            handleFilesChosen (e) {
                this.$emit('chosen', e.target.files)
            }
        }
    }
</script>