<script>
    import { onMount } from 'svelte';
    export let data
    onMount(() =>{
        var buttonLeft = document.querySelector("button:first-of-type")
        var buttonRight = document.querySelector("button:last-of-type")
        var scroller = document.querySelector(".scroller")
        const itemWidth = document.querySelector('img').clientWidth;
        console.log(scroller)
        buttonLeft.addEventListener("click", () => {
            console.log(itemWidth)
            scroller.scrollBy({left: -100, top: 0, behavior: 'smooth'})
        })
        buttonRight.addEventListener("click", () => {
            console.log("hello")
            scroller.scrollBy({left: 100, top: 0, behavior: 'smooth'})
        })
        
    })
</script>
<section>
    <button></button>
    <ul class="scroller">
        {#each data as img}
            <li>
                <picture>
                    <source srcset="{img.image[1].url}" type="image/webp">
                    <img alt="" src="{img.image[0].url}" id="{img.length}" loading="lazy">     
                </picture>
            </li>
        {/each}
    </ul>
    <button></button>
</section>

<style>
    section {
        grid-area: image;
        width: 100%;
        height: 500px;
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
    button {
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
        top: 9em;   
        left: 20em;
    }
</style>