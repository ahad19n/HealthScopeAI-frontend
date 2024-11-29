<script>
	import Router from 'svelte-spa-router'
	import Auth from './routers/auth/Auth.svelte';

	const routes = {
		'/auth/*': Auth,
	}
</script>

<Router {routes}/>
