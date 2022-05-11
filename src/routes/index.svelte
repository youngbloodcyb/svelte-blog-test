<script context="module">
    export const load = async({fetch}) => {
        const res = await fetch("https://jsonplaceholder.typicode.com/posts");
        const posts = await res.json();
        return {
            props: {
                posts,
            }
        }
    }
</script>

<script>
    export let posts
</script>

<img src="/images/cat.jpg" id="cat">

<h1>posts</h1>

<div class="posts">
    {#each posts as item}
        <div class="post">
            <h2>{item.title.substring(0, 20)}...</h2>
            <p>{item.body.substring(0, 80)}...</p>
            <p class="link">
                <a href={`/blog/${item.id}`}>Read More</a>
            </p>
        </div>
    {/each}
</div>

<style global>
    @import url('https://fonts.googleapis.com/css2?family=Space+Mono&display=swap');
    
    * {
    font-family: 'Space Mono', monospace;
    }

    h1 {
    font-size: 48px;
    text-align: center;
    }

    h2 {
        font-size: 18px;
        margin: 0;
    }

    p {
        font-size: 14px;
    }

    .posts {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 20px;
    }

    .post {
        
    }

    .link {
        text-align: right;
    }

    #cat {
        display: block;
        margin-left: auto;
        margin-right: auto;
    }
</style>