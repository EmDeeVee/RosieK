<script setup>
    import { ref, computed } from 'vue'
    import Home from "./components/Home.vue"
    // import Question from "./components/Question.vue"
    // import Subscribe from "./components/Subscribe.vue"

    const routes = {
        '/': Home,
        // '/question': Question,
        // '/subscribe': Subscribe,
    }

    const currentPath = ref(window.location.hash)

    window.addEventListener('hashchange', () => {
        currentPath.value = window.location.hash
    })

    const currentView = computed(() => {
        return routes[currentPath.value.slice(1) || '/' ]
    })

</script>

<template>
     <section class="flex justify-center items-center">
        <div id="frame" class="container mt-6 justify-center max-w-screen-md relative">
            <component :is="currentView" /> 
        </div>
    </section>
</template>

