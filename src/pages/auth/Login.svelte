<script>
    import { fade } from 'svelte/transition';
    import AuthInputField from '../../components/auth/AuthInputField.svelte';
    import AuthActionButton from '../../components/auth/AuthActionButton.svelte';
    import AuthOauthOptions from '../../components/auth/AuthOauthOptions.svelte';

    let isLoading = false;
</script>

<style>
    hr {
        height: 0px;
        width: 150px;
    }
    .divider {
        width: 85%;
        display: flex;
        align-items: center;
        justify-content: space-around;
    }
</style>

<div class="auth-content-root" in:fade>
    <h1>Log In</h1>

    <AuthOauthOptions />
    <div class="divider"><hr><p>or</p><hr></div>

    <div class="auth-input-container">
        <AuthInputField type="name" placeholder="Your name" />
        <AuthInputField type="email" placeholder="Your email" />
    </div>

    <AuthActionButton text="Log In" {isLoading} onClick={async () => {
        isLoading = true;
        await new Promise((resolve) => setTimeout(resolve, 2000));
        isLoading = false;
    }} />

    <p>Dont have an account yet? <a style="color: #CB92FC;" href="/#/auth/signup">Sign Up.</a></p>
    <p>Forgot your password? <a style="color: #CB92FC;" href="/#/auth/forgot">Reset It.</a></p>
</div>
