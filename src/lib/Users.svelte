<script>
    import user1 from "../assets/images/user1.png";
    import user2 from "../assets/images/user2.png";
    import user3 from "../assets/images/user3.png";
    import User from "./User.svelte"
    let users = [
        {
            id:1,
            image: user1,
            name: "永井",
            email: "nagai.hamaya@gmail.com",
        },
        {
            id:2,
            image: user2,
            name: "まさ",
            email: "masa.hamaya@gmail.com",
        },
         {
            id:3,
            image: user3,
            name: "anonymous",
            email: "anonymous.hamaya@gmail.com",
        },
    ];
    const getUsers = () =>{
        return users;
    };
</script>

<div>
    <h1 class="text-2xl text-center mt-10">ユーザーリスト</h1>
    {#each getUsers() as user,i(user.id)}
    <User {user} {i}/>
    {:else}
        <p>ユーザーはいません</p>
    {/each}
</div>
