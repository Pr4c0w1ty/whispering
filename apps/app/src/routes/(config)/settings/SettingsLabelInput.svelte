<script lang="ts">
import { Input } from '$lib/components/ui/input';
import { Label } from '$lib/components/ui/label';
import type { HTMLInputAttributes } from 'svelte/elements';

let {
	id,
	label,
	value,
	type = 'text',
	placeholder = '',
	disabled = false,
	...restProps
}: HTMLInputAttributes & {
	label: string;
	value: string;
	type?: 'text' | 'password';
	placeholder?: string;
	disabled?: boolean;
} = $props();
</script>

<Label class="text-sm" for={id}>{label}</Label>
<Input {id} bind:value {placeholder} {type} {disabled} autocomplete="off" {...restProps} />
