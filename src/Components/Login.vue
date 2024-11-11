<template>
    <div id="login" class="card">
        <h1>Login</h1>
        <form @submit.prevent="emitLogin">
            <div class="container">
                <label for="email">E-mail:</label>
                <input v-model="email" placeholder="Email:" />
                <br>
                <label for="senha">Senha:</label>
                <input v-model="senha" type="password" id="senha" name="senha" />
                <button type="submit" class="animated-button">Entrar</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: "Login",
    data() {
        return {
            email: "",
            senha: ""
        }
    },
    methods: {
        emitLogin() {
            // Verifica se o email e a senha estão corretos
            if (this.email === "Leonardo@gmail.com" && this.senha === "123") {
                console.log("Email: " + this.email);
                this.$emit("login", this.email);
            } else {
                // Exibe uma mensagem de erro se as credenciais estiverem erradas
                alert("Senha errada!"); // Usando alert para mostrar a mensagem
            }
        },
    }
}
</script>

<style scoped>
.card {
    background-color: #ffffff; /* White background for the card */
    border-radius: 8px; /* Rounded corners */
    box-shadow:5px 5px 5px 5px;
    padding: 20px; /* Inner spacing */
    margin: 20px; /* Space around the card */
    max-width: 400px; /* Max width for the card */
    margin-left: auto; /* Center horizontally */
    margin-right: auto; /* Center horizontally */
}

h1 {
    font-size: 70px;
}

h1, h2 {
    font-weight: bolder;
    text-align: center;
    font-family: sans-serif;
}

.container {
    display: flex; /* Use flexbox */
    flex-direction: column; /* Stack elements vertically */
    align-items: center; /* Center align items */
    font-size: 20px;
    font-family: Impact, 'Arial Narrow Bold', sans-serif;
}

label {
    margin-bottom: 5px; /* Space between label and input */
}

input {
    margin-bottom: 15px; /* Space between input fields */
    padding: 10px; /* Inner padding for input fields */
    width: 100%; /* Full width of the container */
    max-width: 300px; /* Optional: set a max width for inputs */
    border-radius: 10px; /* Rounded corners for inputs */
    border: 1px solid #ccc; /* Border for inputs */
}

button {
    background-color: #79151c; /* Background color */
    border: none;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    transition: background-color 0.3s, transform 0.3s; /* Smooth transition for background and transform */
    border-radius: 10px; /* Rounded corners for button */
    position: relative; /* For positioning */
    overflow: hidden; /* Hide overflow */
}

.animated-button:hover {
    background-color: #a41d24; /* Darker background color on hover */
    transform: translateY(-5px); /* Move the button up */
    box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2); /* Add shadow on hover */
}

.animated-button:active {
    transform: translateY(2px); /* Move the button down when clicked */
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1); /* Reduce shadow on click */
}
</style>