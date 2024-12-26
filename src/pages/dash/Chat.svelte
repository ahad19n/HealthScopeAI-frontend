<div class="messages">
    <div class="message bot">Hello! How can I assist you today?</div>
    <div class="message user">Hello! How can I assist you today?</div>
    <div class="message bot">Hello! How can I assist you today?</div>
    <div class="message user">Hello! How can I assist you today?</div>
    <div class="message bot">Hello! How can I assist you today?</div>
    <div class="message user">Hello! How can I assist you today?</div>
    <div class="message bot">Hello! How can I assist you today?</div>
    <div class="message user">Hello! How can I assist you today?</div>
    <div class="message bot">Hello! How can I assist you today?</div>
    <div class="message user">Hello! How can I assist you today?</div>
    <div class="message bot">Hello! How can I assist you today?</div>
    <div class="message user">Hello! How can I assist you today?</div>
</div>

<div class="input-container">
    <textarea placeholder="Type a message..."></textarea>
    <button>Send</button>
</div>

<style>
    .messages {
        flex-grow: 1;
        overflow-y: auto;
        padding: 1rem;
        background-color: #212121;
        margin-left: 10vw;
    }

    .message {
        margin-bottom: 1rem;
        max-width: 75%;
        word-wrap: break-word;
    }

    .message.user {
        align-self: flex-end;
        background-color: #303030;
        color: #ffffff;
        padding: 0.75rem 1rem;
        border-radius: 8px 8px 0 8px;
        margin-left: 25vw;
    }

    .message.bot {
        align-self: flex-start;
        padding: 0.75rem 1rem;
        border-radius: 8px 8px 8px 0;
    }

    .input-container {
        display: flex;
        padding: 1rem;
        background-color: #212121;
        border-top: 1px solid #565869;
    }

    .input-container textarea {
        flex-grow: 1;
        padding: 0.75rem;
        border: none;
        border-radius: 5px;
        font-size: 1rem;
        outline: none;
        resize: none;
        background-color: #2f2f2f;
        color: #ffffff;
        height: 3rem;
    }

    .input-container button {
        margin-left: 0.5rem;
        padding: 0.75rem 1rem;
        border: none;
        border-radius: 5px;
        background-color: #19c37d;
        color: #ffffff;
        font-size: 1rem;
        cursor: pointer;
    }

    .input-container button:hover {
        background-color: #13a067;
    }
</style>