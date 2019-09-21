<script>
/* 
 USE THIS COMPONENT WHEN YOU MAKE A FULL AUTH SYSTEM WITH LARAVEL
*/
export default {
    
}
</script>

<template>
    <div class='login login-background'>
        <div class='login-background-overlay'>
            <div class='login-interface'>
                <img src='../../../src/assets/logo.png' />
                <input placeholder="Username:" class='login-input' />
                <input placeholder="password" class='login-input' type="password" />
                <div class='login-submit' v-on:click="loggedin = true">Submit</div>
            </div>
        </div>
    </div>
</template>
