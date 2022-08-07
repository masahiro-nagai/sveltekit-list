<script>
    export let user;
    export let i;
</script>
<div  class="flex m-5 bg-red border p-2 rounded-lg shadow-md hover:shadow-lg cursor-pointer items-center">
    <p class="w-4">{i + 1}</p>
    <img class="rounded-full w-14 h-14" src={user.image} alt={user.name} />
    <p class="mx-4 w-20">{user.name}</p>
    <p class="mx-4 w-auto">{user.email}</p>
</div>