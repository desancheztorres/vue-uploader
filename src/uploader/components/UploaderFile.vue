<template>
    <div class="bg-white rounded-lg p-4 flex items-stretch mb-1">
        <div>
        </div>
        <div class="flex flex-col justify-between">
            <div class="mb-2">
                <div class="font-medium mr-3 text-gray-700 leading-tight">
                    {{ upload.file.name }}
                </div>
                <div class="text-gray-600 text-sm leading-tight">
                    2 MB
                </div>
            </div>

            <div class="text-gray-600 text-sm align-baseline">
                Cancelled
            </div>

        </div>
    </div>
</template>

<script>
    export default {
        props: {
            upload: {
                required: true,
                type: Object
            }
        }
    }
</script>