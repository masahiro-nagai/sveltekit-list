<script>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();
    function close(){
        dispatch("close");
    }
</script>

<div
    class="relative z-10"
    aria-labelledby="modal-title"
    role="dialog"
    aria-modal="true"
>
    <div class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity" />

    <div class="fixed z-10 inset-0 overflow-y-auto">
        <div
            class="flex items-center sm:items-center justify-center min-h-full p-4 text-center sm:p-0"
        >
            <div
                class="relative bg-white rounded-lg px-4 pb-4 text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:max-w-sm sm:w-full sm:p-6"
            >
                <form class="mt-5 sm:mt-6 bg-white">
                    <slot />
                    <div class="flex justify-between">
                        <button class="px-2 py-1 bg-white text-black border-solid border-1 border-gray-200 rounded hover:bg-gray-400 "
                        on:click={close}>Close</button>
                        <slot name="right-button" />
                    </div>
                </form>
            </div>
        </div>
    </div>
</div>
