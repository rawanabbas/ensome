<script lang="ts">
    export let content : string
    // export let icon : string
    // export let iconAlt : string
</script>
<button class="flex flex-row rounded-none bg-blue-500 text-white p-3">
    <slot></slot>
    {content}
</button>