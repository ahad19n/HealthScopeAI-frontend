<script>
    import { onMount } from 'svelte';
	import Router from 'svelte-spa-router';

    import Login from './Login.svelte';
    import Reset from './Reset.svelte';
    import Forgot from './Forgot.svelte';
    import Signup from './Signup.svelte';
    import Onboarding from './Onboarding.svelte';

    const routes = {
		'/login': Login,
        '/reset': Reset,
        '/forgot': Forgot,
        '/signup': Signup,
        '/onboarding': Onboarding,
	}

    // --------------- Begin Text Changer --------------- //

    const texts = [
        "Emergencies.", "Health Queries.", "Injuries.", "Medical Advice.", "Preventive Care.",
        "Women's Health.", "Mental Health.", "Nutrition.", "First Aid Tips.", "Exercise Tips.",
    ];

    let element;
    let textIndex = 0;
    const delay = 1250;
    const typingSpeed = 100;

    onMount(async () => {
        element = document.getElementById("change");
        cycleTexts();
	});

    function typeText(text, callback) {
        let charIndex = 0;
        const interval = setInterval(() => {
            element.textContent += text[charIndex];
            charIndex++;
            if (charIndex === text.length) {
                clearInterval(interval);
                setTimeout(callback, delay);
            }
        }, typingSpeed);
    }

    function deleteText(callback) {
        const interval = setInterval(() => {
            const currentText = element.textContent;
            element.textContent = currentText.slice(0, -1);
            if (currentText.length === 0) {
                clearInterval(interval);
                callback();
            }
        }, typingSpeed);
    }

    function cycleTexts() {
        typeText(texts[textIndex], () => {
            deleteText(() => {
                textIndex = (textIndex + 1) % texts.length;
                cycleTexts();
            });
        });
    }

    // ---------------- End Text Changer ---------------- //
</script>

<style>
    .root {
        width: 100%;
        height: 100%;
        display: flex;
        color: white;
    }
    .left {
        width: 65vw;
        height: 100vh;
        display: flex;
        padding-left: 1.25vw;
        flex-direction: column;
        justify-content: space-between;
        background-color: #00002C;
    }
    .right {
        width: 35vw;
        height: 100vh;
        display: flex;
        align-items: center;
        flex-direction: column;
        justify-content: center;
        background-color: #000000;
    }
    .header {
        color: #CB92FC;
        font-size: 2.5vw;
    }
    .footer {
        display: flex;
        color: #afafaf;
        font-size: 1.25vw;
        align-items: center;
    }
    .mobile-only {
        display: none;
    }
    @media (max-width: 999px) {
        .desktop {
            display: none;
        }
        .mobile-only {
            display: block;
        }
        .right {
            width: 100%;
            justify-content: space-around;
        }
        .header {
            font-size: 2.5em;
            margin-bottom: 0;
        }
        .footer {
            font-size: 1em;
        }
    }
</style>

<div class="root">
    <div class="left desktop">
        <h2 class="header">HealthScopeAI</h2>
        <h1 style="font-size: 4.25vw; padding-bottom: 2.5rem;">
            Your personal medical<br>assistant for
            <span id="change" style="color: #CB92FC;"></span>
        </h1>
        <div class="footer">
            <p>
                <a style="margin-right: 10px;" href="/#/about/terms">Terms of Use</a>|
                <a style="margin-left: 10px;" href="/#/about/privacy">Privacy Policy</a>
            </p>
        </div>
    </div>
    <div class="right">
        <h2 class="header mobile-only">HealthScopeAI</h2>
        <Router prefix="/auth" {routes} />
        <div class="footer mobile-only">
            <p>
                <a style="margin-right: 10px;" href="/#/about/terms">Terms of Use</a>|
                <a style="margin-left: 10px;" href="/#/about/privacy">Privacy Policy</a>
            </p>
        </div>
    </div>
</div>
