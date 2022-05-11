<script context="module">
    export const load = async ({fetch, params}) => {
        const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${params.id}`)

        const post = await res.json();
        
        return {
            props: {
                post,
            },
        };
    };
</script>

<script>
    export let post; 
</script>
<a href={"/"}>
    <img src="/images/cat.jpg" id="cat">
</a>
<h2>{post.title}</h2>
<p>{post.body}</p>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Space+Mono&display=swap');
    
    * {
    font-family: 'Space Mono', monospace;
    }

    h1 {
    font-size: 48px;
    }

    h2 {
        font-size: 18px;
        margin: 0;
        text-align: center;
    }

    p {
        font-size: 14px;
    }

    #cat {
        display: block;
        margin-left: auto;
        margin-right: auto;
        margin-bottom: 40px;
    }
</style>