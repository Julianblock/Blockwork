<template>
    <div class="header">
        <div class="header-section" v-on:click="dropdown = !dropdown" >
            <div class='header-profile-dropdown'>
                <img src='../../assets/profile-pic.jpg' class="header-profile-pic" />
                <div class="header-item">Hello Julian</div>
            </div>
            <div v-if="dropdown" class="header-profile-dropdown-content"> 
                 <div class="header-profile-dropdown-item">Settings</div>
                 <div class="header-profile-dropdown-item">Logout</div>
            </div>
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