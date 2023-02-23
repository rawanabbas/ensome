<script lang="ts">
	export let name: string;
	let isDropdownOpen = false; // default state (dropdown close)

	const handleDropdownClick = () => {
		isDropdownOpen = !isDropdownOpen; // togle state on click
	};

	const handleDropdownFocusLoss = ({ relatedTarget, currentTarget }) => {
		// use "focusout" event to ensure that we can close the dropdown when clicking outside or when we leave the dropdown with the "Tab" button
		if (relatedTarget instanceof HTMLElement && currentTarget.contains(relatedTarget)) return; // check if the new focus target doesn't present in the dropdown tree (exclude ul\li padding area because relatedTarget, in this case, will be null)
		isDropdownOpen = false;
	};
</script>

<div class="flex justify-between items-center">
	<div class="dropdown" on:focusout={handleDropdownFocusLoss}>
        <button on:click={handleDropdownClick} class="flex flex-row items-center justify-center">
            {name}
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 32 32">
                <path fill="currentColor" d="M16 22L6 12l1.4-1.4l8.6 8.6l8.6-8.6L26 12z" />
            </svg>
        </button>
        <ul class="dropdown-content absolute menu p-2 shadow bg-white rounded-box w-52 z-10" style:display={isDropdownOpen ? 'block' : 'none'}>
			<li><button class="btn text-slate-300">Item 1</button></li>
			<li><button class="btn text-slate-300">Item 2</button></li>
		</ul>
	</div>
</div>
