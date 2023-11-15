<script>
    export let data
</script>
<section>
    <ul>
        {#each data as img}
            <li>
                <img alt="" src="{img.url}">
            </li>
        {/each}
    </ul>
</section>

<style>
    section {
        /* grid-area: auto; */
        width: 100%;
        overflow: hidden;
    }
    ul {
        display: flex;
        overflow-x: auto;
        scroll-snap-type: x mandatory;
        scroll-behavior: smooth;
        -webkit-overflow-scrolling: touch;
    }
    li {
        width: 100%;
        scroll-snap-align: start;
        flex-shrink: 0;
        transform-origin: center center;
        overflow-y: hidden;

    }
    img {
        width: 100%; /* veranderd van 10rem naar 100% om het mooi in de container te laten passen */
        height: 100%;
        object-fit: cover;
    }

    img::before {
        
    }
    
</style>