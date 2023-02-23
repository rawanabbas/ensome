<script lang="ts">
    export let content : string
    export let to : string
    let className = '';
    export { className as class };
</script>
<a href={to} class="text-slate-500 hover:text-black {className}">{content}<slot></slot></a>