<template>
    <div class="header">
        <div class="header-section" v-on:click="dropdown != dropdown" >
            <img src='../../assets/profile-pic.jpg' class="header-profile-pic" />
            <div class="header-item">Hello Julian</div>
        </div>
        <div v-if="dropdown" class="header-profile-dropdown"> 
             <div class="header-profile-dropdown-item"></div>
             <div class="header-profile-dropdown-item"></div>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            dropdown: false,
        }
    }
}
</script>