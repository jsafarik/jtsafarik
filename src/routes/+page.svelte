<script lang="ts">
	// window is not available during server-side rendering
	const isBrowser = () => typeof window !== 'undefined';
	// Set vh for css trick for phone devices
	// https://css-tricks.com/the-trick-to-viewport-units-on-mobile/
	isBrowser() &&
		document.documentElement.style.setProperty('--vh', `${window.innerHeight * 0.01}px`);
</script>

<main>
	<span>JTSafarik</span>
</main>

<style lang="scss">
	main {
		display: flex;
		align-items: center;
		justify-content: center;
		font-variation-settings: 'wght' 600;
		background-color: #111;
		color: #EEE;

		// Backup for devices not supporting Custom Properties
		min-height: 100vh;
		// Trick for phone devices to count vh only from available viewport, not whole screen
		// https://css-tricks.com/the-trick-to-viewport-units-on-mobile/
		min-height: calc(var(--vh, 1vh) * 100);
	}
</style>
