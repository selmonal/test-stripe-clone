<template>
    <div class="relative">
        <div class="flex items-center cursor-pointer" @click="active = true">
            <div class="mr-2">
                <span class="bg-white flex items-center justify-center w-8 h-8 rounded-full shadow">
                    <svg class="fill-current text-grey-dark h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16">
                        <path d="M3 7.5V12h10V7.5c.718 0 1.398-.168 2-.468V15a1 1 0 0 1-1 1H2a1 1 0 0 1-1-1V7.032c.602.3 1.282.468 2 .468zM0 3L1.703.445A1 1 0 0 1 2.535 0h10.93a1 1 0 0 1 .832.445L16 3a3 3 0 0 1-5.5 1.659C9.963 5.467 9.043 6 8 6s-1.963-.533-2.5-1.341A3 3 0 0 1 0 3z" fill-rule="evenodd"></path>
                    </svg>
                </span>
            </div>

            <div class="mr-2">
                <div class="font-bold">Unnamed Account</div>
                <a class="text-indigo font-semibold text-sm">
                    <svg class="fill-current text-grey-dark inline-block h-3 w-3" viewBox="0 0 20 20" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                        <path d="M12.2928932,3.70710678 L0,16 L0,20 L4,20 L16.2928932,7.70710678 L12.2928932,3.70710678 Z M13.7071068,2.29289322 L16,0 L20,4 L17.7071068,6.29289322 L13.7071068,2.29289322 Z" id="Combined-Shape"></path>
                    </svg>
                    Add a name
                </a>
            </div>

            <div>
                <svg class="fill-current text-grey-dark inline-block h-3 w-3" viewBox="0 0 20 20" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                    <path d="M13.591 5.293a1 1 0 0 1 1.416 1.416l-6.3 6.3a1 1 0 0 1-1.414 0l-6.3-6.3A1 1 0 0 1 2.41 5.293L8 10.884z" fill-rule="evenodd"></path>
                </svg>
            </div>
        </div>

        <transition name="fade">
            <div v-if="active" class="absolute pin-t bg-white w-full shadow rounded py-1">
                <div class="group flex hover:bg-indigo items-center cursor-pointer" v-for="i in [1,2,3,4,5]">
                    <div class="p-1 mr-2">
                        <span class="bg-white flex items-center justify-center w-6 h-6 rounded-full shadow">
                            <svg class="fill-current text-grey-dark h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16">
                                <path d="M3 7.5V12h10V7.5c.718 0 1.398-.168 2-.468V15a1 1 0 0 1-1 1H2a1 1 0 0 1-1-1V7.032c.602.3 1.282.468 2 .468zM0 3L1.703.445A1 1 0 0 1 2.535 0h10.93a1 1 0 0 1 .832.445L16 3a3 3 0 0 1-5.5 1.659C9.963 5.467 9.043 6 8 6s-1.963-.533-2.5-1.341A3 3 0 0 1 0 3z" fill-rule="evenodd"></path>
                            </svg>
                        </span>
                    </div>

                    <div class="font-bold text-grey-darker group-hover:text-white">
                        Untitled Store
                    </div>
                </div>

                <div class="group flex hover:bg-indigo items-center cursor-pointer">
                    <div class="p-1 mr-2">
                        <span class="bg-white flex items-center justify-center w-6 h-6 rounded-full shadow">
                            <svg class="fill-current text-grey-dark h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16">
                                <path d="M9 7h6a1 1 0 0 1 0 2H9v6a1 1 0 0 1-2 0V9H1a1 1 0 1 1 0-2h6V1a1 1 0 1 1 2 0z" fill-rule="evenodd"></path>
                            </svg>
                        </span>
                    </div>

                    <div class="font-bold text-grey-darker group-hover:text-white">
                        Add New Store
                    </div>
                </div>
            </div>
        </transition>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                active: false,
            };
        },

        mounted() {
            window.document.addEventListener('click', (event) => {
                if (this.active && ! this.$el.contains(event.target)) {
                    this.active = false;
                }
            });
        },
    }
</script>

<style type="text/css">
.fade-enter-active, .fade-leave-active {
  transition: opacity .3s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
</style>
