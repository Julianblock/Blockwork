<template>
<div class='home'>
    <div class='home-row'> 
        <div class='home-greeting'>
            <img src='../../assets/profile-pic.jpg' class="home-photo"/>
            <h1>Welcome back Julian!</h1>
        </div>
        <div class="home-half">
            <Graph />
        </div>
    </div>
    <div class="home-row">
        <Post />
    </div>
    <div class='home-row'>
        
    </div>
</div>
</template>

<script>
import Graph from './graph.vue';
import Post from './post.vue';

export default {
    components: {
        Graph,
        Post,
    }
}
</script>