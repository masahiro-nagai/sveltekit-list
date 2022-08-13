<script>
    import Modal from "./Modal.svelte";
    let showModal = true;

</script>
    <div class="mt-5">
        <button  on:click={() =>(showModal = true)} class="px-4 py-1 bg-blue-700 text-white rouded cursor-pointer">New User</button> 
        {#if showModal}
            <Modal on:close={()=>(showModal=false)}>
                <h1 class="text-2xl text-center text-black">Create new user</h1>
                    <div class="px-2 py-1 my-4">
                        <label class="text-black" for="">Name</label>
                        <input class="px-2 py-1 w-full rounded border text-black bg-white" type="text" />
                    </div>
                    <div class="px-2 py-1 my-4">
                        <label class="text-black" for="">Email</label>
                        <input class="px-2 py-1 w-full rounded border text-black bg-white" type="email" />
                    </div>
                    <div class="px-2 py-1 my-4 flex justify-between">
                        <label class="text-black" for="true">Active</label>
                        <div class="flex">
                        <label class="text-black" for="true">Yes</label>
                            <input class="px-2 py-1 w-full rounded border text-black bg-white mx-5" 
                            type="radio" 
                            value="true" 
                            id="true" 
                            name="active"/>
                            <label class="text-black" for="false">No</label>
                            <input class="px-2 py-1 w-full rounded border text-black bg-white mx-5" 
                            type="radio" 
                            value="false" 
                            id="false"
                            name="active"/>
                        </div>
                    </div>
                    
                <button type="submit" slot="right-button" class="px-2 py-1 bg-blue-800 text-white rounded">Create</button>
            </Modal>
        {/if}
    </div>