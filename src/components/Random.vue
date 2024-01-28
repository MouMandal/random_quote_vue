<template>
    <div class="container">
        <div class="context">
            <h2>Quote of the Day</h2>
            <p>
                <q> {{ currentQuote.title }} </q>
            </p>
            <h4>{{ currentQuote.author }}</h4>
            <button @click="getRandom">Get Quote</button>
        </div>
    </div>
</template>
  
<script setup>
import { ref, onMounted } from 'vue';
const obj = ref([
    {
        title: "When you have a dream, you've got to grab it and never let go.",
        author: "— Carol Burnett",
    },
    {
        title: "Nothing is impossible. The word itself says 'I'm possible!'",
        author: "— Audrey Hepburn",
    },
    {
        title: "There is nothing impossible to they who will try.",
        author: "— Alexander the Great"
    },
    {
        title: "The bad news is time flies. The good news is you're the pilot.",
        author: "— Michael Altshuler",
    },
])
const currentQuote = ref({ title: "", author: "" });
const getRandom = () => {
    const Random = Math.floor(Math.random() * obj.value.length);
    currentQuote.value = obj.value[Random];
}
onMounted(getRandom);
</script>