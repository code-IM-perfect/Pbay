<script lang="ts">
	export let txt = 'text';
	export let size = '3';
	export let t = 'auto';
	export let b = 'auto';
	export let r = 'auto';
	export let l = 'auto';
	export let rot = '20';
	export let klass = 'question';
	export let z = '-1';
	export let color = 'bg-blue-200';
</script>

<div
	class="{klass} qPopup rounded-full {color} text-black absolute"
	style="top: {t}em; bottom: {b}em; right: {r}em; left: {l}em;font-size:{size}rem; z-index:{z}; rotate:{rot}deg;"
>
	<p class="text-center" style="padding: {(+size * 4) / 3}rem;">{txt}</p>
</div>
