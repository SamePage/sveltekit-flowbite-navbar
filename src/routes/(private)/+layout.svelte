<script lang="ts">
  import {
    Dropdown,
    DropdownDivider,
    DropdownItem,
    Navbar,
    NavBrand,
    NavHamburger,
    NavLi,
    NavUl,
  } from 'flowbite-svelte';

  import { goto } from '$app/navigation';
  import { page } from '$app/stores';
  import { Icon } from 'flowbite-svelte-icons';

  const handleClickLogout = () => {
    void goto('/');
  };

  $: activeUrl = $page.url.pathname;
</script>

<Navbar let:hidden let:toggle>
  <NavBrand class="cursor-default" href="/">
    <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white"
      >activeUrl: {activeUrl}</span
    >
  </NavBrand>
  <NavHamburger on:click={toggle} />
  <NavUl {activeUrl} {hidden}>
    <NavLi href="/page-1">Page-1</NavLi>
    <NavLi href="/page-2">Page-2</NavLi>
    <NavLi href="/page-3">Page-3</NavLi>
    <NavLi id="user-menu" class="cursor-pointer">
      Dropdown Menu
      <Icon
        name="chevron-down-outline"
        class="w-3 h-3 ml-2 text-primary-800 dark:text-white inline"
      />
    </NavLi>
    <Dropdown triggeredBy="#user-menu" class="w-44 z-20">
      <DropdownItem href="/page-4">Page-4</DropdownItem>
      <DropdownDivider />
      <DropdownItem on:click={handleClickLogout}>Home</DropdownItem>
    </Dropdown>
  </NavUl>
</Navbar>
<div class="flex flex-col justify-center items-center p-3 dark:text-white">
  <div>activeUrl: {activeUrl}</div>
  <slot />
</div>
