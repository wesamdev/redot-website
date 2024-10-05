<script>
    import { onMount } from 'svelte';

    let selectedTheme = 'light'; // Default theme

    // Load the saved theme from local storage on mount
    onMount(() => {
        const savedTheme = localStorage.getItem('theme');
        if (savedTheme) {
            selectedTheme = savedTheme;
            applyTheme(savedTheme); // Apply the saved theme
        } else {
            applyTheme(selectedTheme); // Apply the default theme
        }
    });

    function changeTheme(event) {
        selectedTheme = event.target.value;
        localStorage.setItem('theme', selectedTheme); // Save theme to local storage
        applyTheme(selectedTheme); // Apply the selected theme
    }

    function applyTheme(theme) {
        // Set the data-theme attribute on the <html> element
        document.documentElement.setAttribute('data-theme', theme);
    }
</script>

<main class="min-h-screen flex flex-col">
    <!-- Theme Selection -->
    <div class="absolute top-5 right-5 z-10">
        <div class="dropdown">
            <label tabindex="0" class="btn m-1">
                Theme
                <svg
                    width="12px"
                    height="12px"
                    class="inline-block h-2 w-2 fill-current opacity-60"
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 2048 2048">
                    <path d="M1799 349l242 241-1017 1017L7 590l242-241 775 775 775-775z"></path>
                </svg>
            </label>
            <ul tabindex="0" class="dropdown-content bg-base-300 rounded-box z-[1] w-52 p-2 shadow-2xl">
                <li class="mt-2">
                    <label class="flex items-center space-x-2 cursor-pointer">
                        <input
                            type="radio"
                            name="theme-dropdown"
                            class="radio radio-primary"
                            value="light"
                            bind:group={selectedTheme}
                            on:change={changeTheme} />
                        <span>Light</span>
                    </label>
                </li>
                <li class="mt-2">
                    <label class="flex items-center space-x-2 cursor-pointer">
                        <input
                            type="radio"
                            name="theme-dropdown"
                            class="radio radio-primary"
                            value="dark"
                            bind:group={selectedTheme}
                            on:change={changeTheme} />
                        <span>Dark</span>
                    </label>
                </li>
                <li class="mt-2">
                    <label class="flex items-center space-x-2 cursor-pointer">
                        <input
                            type="radio"
                            name="theme-dropdown"
                            class="radio radio-primary"
                            value="cupcake"
                            bind:group={selectedTheme}
                            on:change={changeTheme} />
                        <span>Cupcake</span>
                    </label>
                </li>
                <li class="mt-2">
                    <label class="flex items-center space-x-2 cursor-pointer">
                        <input
                            type="radio"
                            name="theme-dropdown"
                            class="radio radio-primary"
                            value="business"
                            bind:group={selectedTheme}
                            on:change={changeTheme} />
                        <span>Business</span>
                    </label>
                </li>
                <li class="mt-2 mb-2">
                    <label class="flex items-center space-x-2 cursor-pointer">
                        <input
                            type="radio"
                            name="theme-dropdown"
                            class="radio radio-primary"
                            value="wireframe"
                            bind:group={selectedTheme}
                            on:change={changeTheme} />
                        <span>Wireframe</span>
                    </label>
                </li>
            </ul>
        </div>
    </div>

    <!-- Hero Section -->
    <section class="hero bg-base-200 flex items-center justify-center text-center p-10">
        <div class="max-w-3xl">
            <h1 class="text-5xl font-bold">Welcome to Redot Engine</h1>
            <p class="mt-4 text-xl">The intuitive game engine for everyone.</p>
            <a href="/get-started" class="btn btn-primary mt-6">Get Started</a>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features py-20">
        <h2 class="text-4xl font-bold text-center mb-10">Key Features</h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-10 px-5">
            <div class="card bg-base-100 shadow-lg p-5">
                <div class="card-body">
                    <h3 class="text-xl font-semibold">Feature 1</h3>
                    <p>Description of feature 1. Explain what makes it unique.</p>
                </div>
            </div>
            <div class="card bg-base-100 shadow-lg p-5">
                <div class="card-body">
                    <h3 class="text-xl font-semibold">Feature 2</h3>
                    <p>Description of feature 2. Highlight its benefits.</p>
                </div>
            </div>
            <div class="card bg-base-100 shadow-lg p-5">
                <div class="card-body">
                    <h3 class="text-xl font-semibold">Feature 3</h3>
                    <p>Description of feature 3. Mention any relevant details.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer Section -->
    <footer class="footer bg-base-300 p-10">
        <div class="container mx-auto text-center">
            <p class="text-gray-600">© 2024 Redot Engine. All rights reserved.</p>
            <div class="flex justify-center space-x-4 mt-4">
                <a href="#" class="link">Privacy Policy</a>
                <a href="#" class="link">Terms of Service</a>
            </div>
        </div>
    </footer>
</main>

<style>
    .hero {
        min-height: 60vh;
    }
</style>