<script lang="ts">
	interface Props {
		isCollapsed: boolean;
		onClick: () => void;
		classNames: string;
	}

	let { isCollapsed, classNames, onClick }: Props = $props();
</script>

<button
	onclick={onClick}
	class="{classNames} group flex h-16 w-6 flex-col items-center justify-center -space-y-1 outline-none *:h-3 *:w-1 *:rounded-full *:hover:bg-gray-300 dark:*:hover:bg-gray-600 max-md:hidden {!isCollapsed
		? '*:bg-gray-200/70 dark:*:bg-gray-800'
		: '*:bg-gray-200 dark:*:bg-gray-700'}"
	name="sidebar-toggle"
	aria-label="Toggle sidebar navigation"
>
	<div class={!isCollapsed ? "group-hover:rotate-[20deg]" : "group-hover:-rotate-[20deg]"}></div>
	<div class={!isCollapsed ? "group-hover:-rotate-[20deg]" : "group-hover:rotate-[20deg]"}></div>
</button>
