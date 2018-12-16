<template>
    <div class="container mx-auto mt-6">
        <div class="fixed h-screen w-sb">
            <dropdown></dropdown>
        </div>

        <div class="pl-sb">
            <div class="pl-4">
                <div class="bg-indigo w-full">
                    Body Header
                </div>

                <div class="bg-blue" style="height: 1000px;">
                    <nuxt/>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import Dropdown from '~/components/Dropdown';

    export default {
        components: {
            Dropdown,
        },
    }
</script>
