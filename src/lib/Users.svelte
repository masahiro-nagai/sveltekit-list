<script>
    import user1 from "../assets/images/user1.png";
    import user2 from "../assets/images/user2.png";
    import user3 from "../assets/images/user3.png";
    import FilterUser from "./FilterUser.svelte";
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
    $:filteredUsers = users;

    const filter = ({detail}) => {
        if(detail === "null"){
            filteredUsers = users;
            return;
        }
        const active = detail === "true";
        filteredUsers = users.filter((user) => user.active === active);
    };

    const remove = ({detail}) =>{
        users = users.filter((user) => user.id !== detail)
    };
</script>

<div>
    <h1 class="text-2xl text-center mt-10">ユーザーリスト</h1>
    <FilterUser on:filter={filter}/>
    {#each filteredUsers as user, i (user.id)}
        <User on:remove={remove} {user} {i} />
    {:else}
        <p>ユーザーはいません</p>
    {/each}
</div>
