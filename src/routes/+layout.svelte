<script lang="ts">
    import "../app.css";
    import favicon from "$lib/assets/favicon.svg";
    import { BottomNav, BottomNavItem, DarkMode, Tooltip } from "flowbite-svelte";
    import { FileInvoiceSolid, MapPinAltSolid, PhoneSolid } from "flowbite-svelte-icons";

    let { children } = $props();
</script>

<svelte:head>
    <link rel="icon" href={favicon} />
</svelte:head>

<div class="flex items-center justify-between p-3 shadow bg-white dark:bg-gray-800">
    <div class="text-lg font-bold text-gray-800 dark:text-white">UniSafe</div>
    <DarkMode
        class="p-2 rounded-lg border border-gray-300 dark:border-gray-600 
                text-gray-600 dark:text-gray-300 hover:bg-gray-100 dark:hover:bg-gray-700"
    />
</div>

{@render children?.()}

<div class="dark:text-gray-300">
    <BottomNav
        position="absolute"
        navType="application"
        classes={{ inner: "grid-cols-3" }}
    >
        <BottomNavItem>
            <FileInvoiceSolid class="shrink-0 h-6 w-6" />
            <span class="text-xs mt-1">Report</span>
        </BottomNavItem>

        <div class="flex items-center justify-center">
            <BottomNavItem
                btnName="SOS"
                appBtnPosition="middle"
                class="bg-red-600 hover:bg-red-700 group focus:ring-primary-300 dark:focus:ring-primary-800 inline-flex h-14 w-14 items-center justify-center rounded-full font-medium focus:ring-4 focus:outline-hidden flex-col"
            >
                <PhoneSolid class="shrink-0 h-7 w-7 " />
                <span class="text-[10px] text-white">SOS</span>
            </BottomNavItem>
            <Tooltip arrow={false}>SOS</Tooltip>
        </div>

        <BottomNavItem>
            <div class="flex flex-col items-center">
                <MapPinAltSolid class="shrink-0 h-6 w-6" />
                <span class="text-xs mt-1">Map</span>
            </div>
        </BottomNavItem>
    </BottomNav>
</div>
