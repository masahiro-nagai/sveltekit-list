<script>
    import user1 from "../assets/images/user1.png";
    import user2 from "../assets/images/user2.png";
    import user3 from "../assets/images/user3.png";
    import User from "./User.svelte";
    let users = [
        {
            id: 1,
            image: user1,
            name: "永井",
            email: "nagai.hamaya@gmail.com",
            active: false,
        },
        {
            id: 2,
            image: user2,
            name: "まさ",
            email: "masa.hamaya@gmail.com",
            active: true,
        },
        {
            id: 3,
            image: user3,
            name: "anonymous",
            email: "anonymous.hamaya@gmail.com",
            active: false,
        },
    ];
    let filteredUsers = users;

    const filter = (e) => {
        if(e.target.value === "null"){
            filteredUsers = users;
            return;
        }
        const active = e.target.value === "true";
        filteredUsers = users.filter((user) => user.active === active);
    };
</script>

<div>
    <h1 class="text-2xl text-center mt-10">ユーザーリスト</h1>
    <select
        on:change={filter}
        name="user-filter"
        id="user-filter"
        class="border rounded-lg px-4 py-2 ml-4"
    >
        <option value={null}>All</option>
        <option value={true}>Active</option>
        <option value={false}>Inactive</option>
    </select>
    {#each filteredUsers as user, i (user.id)}
        <User {user} {i} />
    {:else}
        <p>ユーザーはいません</p>
    {/each}
</div>
