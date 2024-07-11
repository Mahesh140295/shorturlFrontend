<script setup></script>

<template>
    <div class="container mx-auto px-5 overflow-x-hidden lg:overflow-x-visible">
        <section class="grid grid-cols-none lg:grid-cols-2 pb-16 pt-8 items-center">
            <!-- Left Section Start -->
            <div class="lg:w-5/6 order-2 lg:order-none">
                <h1 class="text-4xl xl:text-5xl font-bold font-theme-heading text-center lg:text-left">
                    Keep your links short and secure!
                </h1>
                <p class="lg:text-xl mt-10 font-theme-content text-theme-grayish-blue text-center lg:text-left">
                    Go beyond short links! Shorten URLs and share them with a select group, but keep the contents a secret. Set expiration dates and track access to your shortened URLs. Know exactly who sees your info, and when it disappears forever.
                </p>
                
            </div>
            <!-- Left Section End -->
            
            <!-- Right Section Start -->
            <div class="relative order-1 lg:order-none mb-20 lg:mt-0 lg:mb-0 lg:-mr-10">
                <div class="bg-white p-8 rounded-lg shadow-md max-w-md w-full mx-auto">
                 <h2 class="text-2xl font-bold mb-6 text-center">Welcome to TwistURL!</h2>
                    <h2 class="text-2xl font-bold mb-6 text-center">Sign In</h2>
                    <form @submit.prevent="handleSubmit">
                        <div class="mb-4">
                            <label class="block text-gray-700 text-sm font-bold mb-2" for="username">
                                Username
                            </label>
                            <input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" id="username" type="text" v-model="username" placeholder="Enter Username" />
                        </div>
                        <div class="mb-6">
                            <label class="block text-gray-700 text-sm font-bold mb-2" for="password">
                                Password
                            </label>
                            <input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline" id="password" type="password" v-model="password" placeholder="Enter Password" />
                        </div>
                        <div class="flex items-center justify-between mb-6">
                            <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline" type="submit">
                                Sign In
                            </button>
                        </div>
                    </form>
                    <div class="text-center">
                        <router-link to="/signup">Don't have an account? Sign-Up</router-link>
                    </div>
                    <div class="mt-6 text-center">
                        <p>Or continue with</p>
                        <div class="flex justify-center mt-4">
                            <button class="flex items-center bg-gray-800 text-white py-2 px-4 rounded mx-2" @click="oauthLogin('github')">
                                <i class="fab fa-github mr-2"></i> GitHub
                            </button>
                            <button class="flex items-center bg-red-600 text-white py-2 px-4 rounded mx-2" @click="oauthLogin('google')">
                                <i class="fab fa-google mr-2"></i> Google
                            </button>
                        </div>
                    </div>
                </div>
            </div>
            <!-- Right Section End -->
        </section>
    </div>
</template>

<script>
export default {
    data() {
        return {
            username: '',
            password: ''
        };
    },
    methods: {
        handleSubmit() {
            // Handle form submission logic
            console.log('Username:', this.username);
            console.log('Password:', this.password);
        },
        oauthLogin(provider) {
            // Handle OAuth login logic
            console.log(`Logging in with ${provider}`);
        }
    }
};
</script>

<style scoped>
.container {
    max-width: 1200px;
}
.bg-theme-primary {
    background-color: #4a90e2;
}
.text-theme-grayish-blue {
    color: #6b7280;
}
button i {
    margin-right: 8px;
}
</style>