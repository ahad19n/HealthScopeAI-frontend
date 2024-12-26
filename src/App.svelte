<script>
	import Router from 'svelte-spa-router';

	import Auth from './pages/auth/Auth.svelte';
	import Dash from './pages/dash/Dash.svelte';

	const routes = {
		'/auth/*': Auth,
		'/dash/*': Dash
	};
</script>

<Router {routes}/>
