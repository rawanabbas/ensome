<script>
    import { Dropdown } from '$lib/components/molecules'
	import { default as NavLogo } from './NavLogo.svelte';
	import { default as NavBtn } from './NavBtn.svelte';
	import { default as NavLink } from './NavLink.svelte';
</script>

<header class="py-8 flex lg-flex flex-row justify-center sticky-top-0">
	<div class="w-3/4 flex flex-row items-center place-content-around">
		<NavLogo />
        <NavLink content="Home" to="#"></NavLink>
        <NavLink content="Solutions" to="#"></NavLink>
        <NavLink content="" to="#">
            <Dropdown name="Pages"></Dropdown>
        </NavLink>
        <NavLink content="Elements" to="#"></NavLink>
        <NavLink content="Blog" to="#"></NavLink>
        <NavLink content="Contacts" to="#"></NavLink>
        <NavBtn content="Watch the demo">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="#fff" stroke="#fff" d="m9.5 16.5l7-4.5l-7-4.5v9ZM12 22q-2.075 0-3.9-.788t-3.175-2.137q-1.35-1.35-2.137-3.175T2 12q0-2.075.788-3.9t2.137-3.175q1.35-1.35 3.175-2.137T12 2q2.075 0 3.9.788t3.175 2.137q1.35 1.35 2.138 3.175T22 12q0 2.075-.788 3.9t-2.137 3.175q-1.35 1.35-3.175 2.138T12 22Zm0-2q3.35 0 5.675-2.325T20 12q0-3.35-2.325-5.675T12 4Q8.65 4 6.325 6.325T4 12q0 3.35 2.325 5.675T12 20Zm0-8Z"/></svg>
        </NavBtn>
	</div>
</header>
