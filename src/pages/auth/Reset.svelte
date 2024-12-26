<script>
    import { fade } from 'svelte/transition';
    import AuthInputField from '../../components/auth/AuthInputField.svelte';
    import AuthActionButton from '../../components/auth/AuthActionButton.svelte';

    let isLoading = false;
</script>

<div class="auth-content-root" in:fade>
    <h1>Password Reset</h1>

    <div class="auth-input-container">
        <AuthInputField type="password" placeholder="New password" />
        <AuthInputField type="password" placeholder="Confirm password" />
    </div>

    <AuthActionButton text="Reset" {isLoading} onClick={async () => {
        isLoading = true;
        await new Promise((resolve) => setTimeout(resolve, 2000));
        isLoading = false;
    }} />

    <a style="color: #CB92FC;" href="/#/auth/login">← Back to Log In.</a>
</div>
