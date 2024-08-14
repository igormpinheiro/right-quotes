<template>
    <div class="quote-container">
      <p class="quote-text">"{{ randomQuote.text }}"</p>
      <p class="quote-author">- {{ randomQuote.author }}</p>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  
  const quotes = [
    { text: "A única coisa necessária para o triunfo do mal é que os homens bons não façam nada.", author: "Edmund Burke" },
    { text: "O problema do socialismo é que, eventualmente, você fica sem o dinheiro dos outros.", author: "Margaret Thatcher" },
    { text: "A liberdade nunca está a mais de uma geração da extinção.", author: "Ronald Reagan" },
    { text: "O vício inerente ao capitalismo é a distribuição desigual das bênçãos; a virtude inerente ao socialismo é a distribuição igual das misérias.", author: "Winston Churchill" },
    { text: "O extremismo em defesa da liberdade não é um vício. E a moderação na busca da justiça não é uma virtude.", author: "Barry Goldwater" },
  ];
  
  const randomQuote = ref({});
  
  const getRandomQuote = () => {
    const randomIndex = Math.floor(Math.random() * quotes.length);
    randomQuote.value = quotes[randomIndex];
  };
  
  onMounted(() => {
    getRandomQuote();
  });
  </script>
  
  <style scoped>
  .quote-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f4f4f4;
    color: #333;
    padding: 20px;
  }
  
  .quote-text {
    font-size: 24px;
    font-style: italic;
    margin-bottom: 15px;
    text-align: center;
  }
  
  .quote-author {
    font-size: 20px;
    font-weight: bold;
    color: #555;
    text-align: center;
  }
  </style>
  