<template>
	<div class="pkpFieldError" aria-live="polite">
		<div
			v-for="message in messages"
			:key="message"
			class="pkpFieldError__message"
		>
			<Icon icon="Error" class="me-1 h-4 w-4 text-on-dark" :inline="true" />
			<span v-strip-unsafe-html="message" />
		</div>
	</div>
</template>

<script>
import Icon from '@/components/Icon/Icon.vue';

export default {
	name: 'FieldError',
	components: {Icon},
	props: {
		messages: Array,
	},
};
</script>

<style lang="less">
@import '../../styles/_import';

.pkpFieldError {
	position: relative;
	display: inline-block;
	margin-top: 0.5rem;
	padding: 0.5rem 1rem;
	border-radius: @radius;
	background: @no;
	color: #fff;
	font-size: 0.9rem;
	line-height: 1.6em;

	&:before {
		content: '';
		position: absolute;
		bottom: 100%;
		left: 1rem;
		border-bottom: 5px solid @no;
		border-left: 5px solid transparent;
		border-right: 5px solid transparent;
	}

	.fa {
		color: #fff;
	}
}

[dir='rtl'] {
	.pkpFieldError {
		&:before {
			left: auto;
			right: 1rem;
		}
	}
}
</style>
