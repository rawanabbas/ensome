<script lang="ts">
    export let content : string
    let className = '';
    export { className as class };
    export let onClick = () => {}
</script>
<button class="flex rounded-none text-white p-3 {className}" on:click={onClick}>
    <slot></slot>
    {content}
</button>