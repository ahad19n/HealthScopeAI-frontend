<script>
	import Router from 'svelte-spa-router';

	import Chat from './Chat.svelte';

	const routes = {
		'/dash/chat': Chat,
	};
</script>

<root>
    <div class="sidebar open">
        <div style="display: flex; justify-content: center; color: #CB92FC"><h2>HealthScopeAI</h2></div>
        <div class="header-buttons">
            <button>
                <div style="display: flex; align-items: center;">
                    <span style="margin-right: 10px;" class="material-icons">question_answer</span>
                    Chat with AI
                </div>
            </button>
            <button>
                <div style="display: flex; align-items: center;">
                    <span style="margin-right: 10px;" class="material-icons">event</span>
                    Medicinal Reminders
                </div>
            </button>
            <button>
                <div style="display: flex; align-items: center;">
                    <span style="margin-right: 10px;" class="material-icons">medication</span>
                    Pharmacy & Deliveries
                </div>
            </button>
            <button>
                <div style="display: flex; align-items: center;">
                    <span style="margin-right: 10px;" class="material-icons">support_agent</span>
                    Support & Feedback
                </div>
            </button>
        </div>
    
        <div class="history" id="history"></div>
    
        <div class="profile">
            <div style="display: flex; align-items: center; padding-top: 10px;">
                <span style="font-size: 40px; margin-right: 10px" class="material-icons">account_circle</span>
                Abdul Ahad
            </div>
            <div style="font-size: 50px">
                <a href="/#/dash/settings"><span class="material-icons">settings</span></a>
                <a href="/#/auth/logout"><span class="material-icons">logout</span></a>
            </div>
    
        </div>
    </div>

    <div class="content-container">
        <Router {routes}/>
    </div>
</root>


<style>
    root {
        margin: 0;
        font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
        display: flex;
        height: 100vh;
        background-color: #212121;
        color: #dcdcdc;
    }

    .sidebar {
        width: 400px;
        background-color: #000000;
        display: flex;
        flex-direction: column;
        position: relative;
        transform: translateX(-400px);
        transition: transform 0.3s ease;
    }

    .sidebar.open {
        transform: translateX(0);
    }

    .sidebar .header-buttons {
        padding: 1rem;
        border-bottom: 1px solid #565869;
    }

    .sidebar .header-buttons button {
        width: 100%;
        padding: 0.75rem;
        margin-bottom: 0.5rem;
        border: none;
        background-color: #000000;
        color: #dcdcdc;
        text-align: left;
        font-size: 1rem;
        cursor: pointer;
        border-radius: 5px;
    }

    .sidebar .header-buttons button:hover {
        background-color: #303030;
    }

    .sidebar .history {
        flex-grow: 1;
        padding: 1rem;
        overflow-y: auto;
    }

    .sidebar .profile {
        padding: 1rem;
        border-top: 1px solid #565869;
        display: flex;
        align-items: center;
        justify-content: space-between;
        position: relative;
    }

    .sidebar .profile img {
        width: 40px;
        height: 40px;
        border-radius: 50%;
        margin-right: 1rem;
    }

    .sidebar .profile span {
        /* font-size: 1rem; */
        color: #dcdcdc;
        cursor: pointer;
    }

    .sidebar .profile a {
        font-size: 1.5rem;
        color: #dcdcdc;
    }

    .profile-popup {
        position: absolute;
        bottom: 60px;
        right: 10px;
        background-color: #444654;
        border-radius: 5px;
        box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
        padding: 1rem;
        display: none;
        flex-direction: column;
    }

    .profile-popup a {
        color: #dcdcdc;
        text-decoration: none;
        padding: 0.5rem 0;
        cursor: pointer;
    }

    .profile-popup a:hover {
        background-color: #565869;
        border-radius: 5px;
    }

    .content-container {
        display: flex;
        flex-direction: column;
        flex-grow: 1;
        overflow: hidden;
        width: 100%;
    }
</style>