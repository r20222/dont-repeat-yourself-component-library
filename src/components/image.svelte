<script>
    import { onMount } from 'svelte';
    export let data
    console.log(data[0].image[0])
    // onMount(() =>{
    //     var buttonLeft = document.querySelector("button:first-of-type")
    //     var buttonRight = document.querySelector("button:last-of-type")
    //     buttonLeft.addEventListener("click", () => { })
    //     buttonRight.addEventListener("click", () => { })
        
    // })
</script>
<section>
    <!-- <button></button> -->
    <ul>
        {#each data as img}
            <li>
                <picture>
                    <source srcset="{img.image[1].url}" type="image/webp">
                    <img alt="" src="{img.image[0].url}" id="{img.length}" loading="lazy">     
                </picture>
            </li>
        {/each}
    </ul>
    <!-- <button></button> -->
</section>

<style>
    section {
        grid-area: image;
        width: 100%;
        height: 100%;
        overflow: hidden;
    }
    ul {
        display: flex;
        overflow-x: auto;
        scroll-snap-type: x mandatory;
        scroll-behavior: smooth;
        -webkit-overflow-scrolling: touch;
        position: absolute;
    }
    li {
        scroll-snap-align: start;
        flex-shrink: 0;
        transform-origin: center center;
        overflow-y: hidden;

    }
    img {
        width: 100%;
        height: 30em;
        object-fit: fill;
    }
    /* button {
        background-color: white;
        width: 5em;
        height: 5em;
        border-radius: 5em;
        position: relative;
        left: 0;
        top: 14em;
        display: block;
        border: 1px white solid;
        z-index: 2;
    }
    
    ul+button {
        left: 32em;
        top: 9em;   
    } */
</style>