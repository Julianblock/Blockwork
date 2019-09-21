<template>
<div>
    <div class='home'>
        <img src='../../assets/profile-pic.jpg' class="home-photo"/>
        <h1>Welcome back Julian!</h1>
    </div>
    <div class="home-half">
        <Graph />
    </div>
</div>
</template>

<script>
import Graph from './graph.vue';

export default {
    components: {
        Graph,
    }
}
</script>