<script lang="ts">
    export let content : string
    export let to : string
</script>
<a href={to} class="text-slate-500 hover:text-black">{content}<slot></slot></a>