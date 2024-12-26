<script>
    import { fade } from 'svelte/transition';
    import AuthInputField from '../../components/auth/AuthInputField.svelte';
    import AuthActionButton from '../../components/auth/AuthActionButton.svelte';

    let isLoading = false;
</script>

<style>
    h1 {
        margin-bottom: 0;
    }
    p {
        margin-top: 5px;
        margin-bottom: 30px;
    }
</style>

<div class="auth-content-root" in:fade>
    <h1>A few more details</h1>
    <p>These are optional, feel free to leave them empty.</p>

    <div class="auth-input-container">
        <AuthInputField type="name" placeholder="Your name" />
        <AuthInputField type="email" placeholder="Your email" />
        <AuthInputField type="password" placeholder="New password" />
        <AuthInputField type="password" placeholder="Confirm password" />
    </div>

    <AuthActionButton text="Continue" {isLoading} onClick={async () => {
        isLoading = true;
        await new Promise((resolve) => setTimeout(resolve, 2000));
        isLoading = false;
    }} />
</div>
