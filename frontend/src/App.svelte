<script>
    import View from "./View.svelte"
    import { AppShell, AppRail, AppRailTile, AppRailAnchor, LightSwitch } from "@skeletonlabs/skeleton"

    import Icon from "@iconify/svelte"

    let currentPage = 0
</script>

<main>
    <AppShell>
        <svelte:fragment slot="header">
            <div class="p-2">
                <LightSwitch class="float-right" />
            </div>
        </svelte:fragment>
        <svelte:fragment slot="sidebarLeft">
            <AppRail>
                <AppRailTile bind:group={currentPage} name="page-dashboard" value={0} title="page-dashboard">
                    <svelte:fragment slot="lead">
                        <Icon icon="fa-solid:home" class="m-auto text-4xl" />
                    </svelte:fragment>
                    <span>Dashboard</span>
                </AppRailTile>
                <AppRailTile bind:group={currentPage} name="page-settings" value={1} title="page-settings">
                    <svelte:fragment slot="lead">
                        <Icon icon="fa-solid:cogs" class="m-auto text-4xl" />
                    </svelte:fragment>
                    <span>Settings</span>
                </AppRailTile>
            </AppRail>
        </svelte:fragment>
        <!-- (sidebarRight) -->
        <!-- (pageHeader) -->
        <!-- Router Slot -->
        <!-- <slot /> -->
        <View page={currentPage} />
        <!-- ---- / ---- -->
        <!-- (pageFooter) -->
        <svelte:fragment slot="footer">Footer</svelte:fragment>
    </AppShell>
</main>

<style>
</style>
