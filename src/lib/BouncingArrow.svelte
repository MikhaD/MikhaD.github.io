<svg class="bounce" viewBox="0 0 10 7" fill="none">
	<path d="M1 1L5 5L9 1" stroke-width="2" stroke="currentcolor" stroke-linecap="round" />
</svg>

<style lang="scss">
	.bounce {
		animation: bouncing-arrow 1.5s infinite;
	}
	@keyframes bouncing-arrow {
		0% {
			transform: translateY(0);
		}
		70% {
			transform: translateY(50%);
		}
		100% {
			transform: translateY(0%);
		}
	}
</style>
