<script>
	import { Dropdown } from '$lib/components/molecules';
	import { default as NavLogo } from './NavLogo.svelte';
	import { default as NavBtn } from './NavBtn.svelte';
	import { default as NavLink } from './NavLink.svelte';

	let isMenuOpen = false;
	let innerWidth = 0;
	const handleMenuClick = () => {
		isMenuOpen = !isMenuOpen;
		console.log('====================================');
		console.log(isMenuOpen);
		console.log('====================================');
	};
</script>

<svelte:window bind:innerWidth />

<header class="nav py-8 flex lg-flex flex-row justify-center sticky-top-0">
	<div class="w-5/6 md:w-3/4 flex flex-row items-center place-content-between">
		<NavLogo />
		{#if isMenuOpen || innerWidth >= 768}
			<div
				class="flex flex-col md:flex-row grow place-content-around items-center {isMenuOpen &&
				innerWidth < 768
					? 'absolute bg-white nav__menu'
					: ''}"
			>
				<NavLink content="Home" to="#" class={innerWidth < 768 ? 'mb-7': ''}/>
				<NavLink content="Solutions" to="#" class={innerWidth < 768 ? 'mb-7': ''}/>
				<NavLink content="" to="#" class={innerWidth < 768 ? 'mb-7': ''}>
					<Dropdown name="Pages" />
				</NavLink>
				<NavLink content="Elements" to="#" class={innerWidth < 768 ? 'mb-7': ''} />
				<NavLink content="Blog" to="#" class={innerWidth < 768 ? 'mb-7': ''} />
				<NavLink content="Contacts" to="#" class={innerWidth < 768 ? 'mb-7': ''} />
				<NavBtn content="Watch the demo" class="flex-row bg-blue-500 {innerWidth < 768 ? 'mb-7': ''}">
					<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
						><path
							fill="#fff"
							stroke="#fff"
							d="m9.5 16.5l7-4.5l-7-4.5v9ZM12 22q-2.075 0-3.9-.788t-3.175-2.137q-1.35-1.35-2.137-3.175T2 12q0-2.075.788-3.9t2.137-3.175q1.35-1.35 3.175-2.137T12 2q2.075 0 3.9.788t3.175 2.137q1.35 1.35 2.138 3.175T22 12q0 2.075-.788 3.9t-2.137 3.175q-1.35 1.35-3.175 2.138T12 22Zm0-2q3.35 0 5.675-2.325T20 12q0-3.35-2.325-5.675T12 4Q8.65 4 6.325 6.325T4 12q0 3.35 2.325 5.675T12 20Zm0-8Z"
						/></svg
					>
				</NavBtn>
			</div>
		{/if}
		<NavBtn class="md:hidden flex flex-col" content="" onClick={handleMenuClick}>
			<span class="w-7 h-0.5 bg-blue-500" />
			<span class="w-7 h-0.5 bg-blue-500 mt-1" />
			<span class="w-7 h-0.5 bg-blue-500 mt-1" />
		</NavBtn>
	</div>
</header>

<style lang="postcss">
    .nav {
        position: relative;
    }

    .nav__menu {
		top: 100%;
		width: 100vw;
		left: -10%;
		padding-left: 23%;
		/* padding-top: 15%; */
        font-size: 1.5rem;
	}
</style>
