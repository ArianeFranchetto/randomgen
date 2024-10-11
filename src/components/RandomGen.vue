<script setup>
import { ref, onMounted } from "vue";

const quotes = ref([
    {
        text: "The only way to do great work is to love what you do.",
        author: "Steve Jobs",
    },
    {
        text: "Believe you can and you're halfway there.",
        author: "Theodore Roosevelt",
    },
    {
        text: "Life is what happens when you're busy making other plans.",
        author: "John Lennon",
    },
    {
        text: "In the end, it's not the years in your life that count, it's the life in your years.",
        author: "Abraham Lincoln"
    },
    {
        text: "The best and most beautiful things in the world cannot be seen or even touched - they must be felt with the heart.",
        author: "Helen Keller"
    },
    {
        text: "The greatest glory in living lies not in never falling, but in rising every time we fall.",

        author: "Nelson Mandela"
    }
]);

const currentQuote = ref({ text: "", author: "" });

const getRandomQuote = () => {
    const randomIndex = Math.floor(Math.random() * quotes.value.length);
    currentQuote.value = quotes.value[randomIndex];
};


onMounted(getRandomQuote);
</script>

<template>
    <div class="quote-generator">
        <h1 class="app-title">Phrase of the day</h1>
        <span class="app-text">What will be your phrase of the day?</span>

        <blockquote class="quote-container">
            <p>{{ currentQuote.text }}</p>
            <cite>{{ currentQuote.author }}</cite>
        </blockquote>

        <button @click="getRandomQuote" class="quote-button">
            Get Phrase
        </button>
    </div>
</template>

<style scoped>
.quote-generator {
    max-width: 400px;
    margin: 50px auto;
    padding: 20px;
    text-align: center;
    border: 1px solid #ccc;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.app-title {
    font-size: 24px;
    margin-bottom: 20px;
    color: #333;
}

.quote-container {
    background-color: #d68080;
    padding: 20px;
    border-radius: 8px;
    border: 1px solid #ddd;
    margin-bottom: 20px;
}

p {
    font-size: 18px;
    margin-bottom: 10px;
}

cite {
    font-style: normal;
    color: #fff3f3;
}

.quote-button {
    padding: 10px 20px;
    font-size: 16px;
    background-color: #3a8b61;
    color: #fff;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

.quote-button:hover {
    background-color: #2980b9;
}</style>