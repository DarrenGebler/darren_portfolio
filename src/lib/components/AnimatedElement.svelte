<script lang="ts">
    import { fade } from 'svelte/transition';
    import { inview } from 'svelte-inview';

    let isInView;
</script>

<div
    class="wrapper"
    use:inview={{ unobserveOnEnter: false, rootMargin: '-30%'}}
    on:change={({detail}) => {
        isInView = detail.inView;
    }}
>
    {#if isInView}
        <div in:fade class="box" out:fade>
            <slot name="animated"/>
        </div>
    {/if}
</div>


<style>
    .box {
        width: 500px;
        padding: 25px;
    }
</style>