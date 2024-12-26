<script>
    import { fade } from 'svelte/transition';
    import AuthInputField from '../../components/auth/AuthInputField.svelte';
    import AuthActionButton from '../../components/auth/AuthActionButton.svelte';

    let isLoading = false;
</script>

<div class="auth-content-root" in:fade>
    <h1>Sign Up</h1>

    <div class="auth-input-container">
        <AuthInputField type="name" placeholder="Your name" />
        <AuthInputField type="email" placeholder="Your email" />
        <AuthInputField type="password" placeholder="New password" />
        <AuthInputField type="password" placeholder="Confirm password" />
    </div>

    <AuthActionButton text="Sign Up" {isLoading} onClick={async () => {
        isLoading = true;
        await new Promise((resolve) => setTimeout(resolve, 2000));
        isLoading = false;
    }} />

    <p>Already have an account? <a style="color: #CB92FC;" href="/#/auth/login">Log In.</a></p>
</div>
