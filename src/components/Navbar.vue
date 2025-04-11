<template>
    <div class="navbar-container">
        <nav>
            <RouterLink to="/">
                <i class="fa-solid fa-house"></i>
            </RouterLink>
            <RouterLink to="/workout" class="create-icon">
                <i class="fa-solid fa-plus"></i>
            </RouterLink>
            <RouterLink to="/statistics">
                <i class="fa-solid fa-chart-line"></i>
            </RouterLink>
        </nav>
    </div>
</template>

<script setup lang="ts">
</script>

<style lang="css" scoped>
    .navbar-container {
        position: absolute;
        bottom: 0;
        width: 100%;
        border-top: 1px solid #888888;
        background-color: rgba(255, 255, 255, 0.04)
    }

    nav {
        display: flex;
        justify-content: space-between;
        align-items: center;


    }

    a {
        flex-grow: 1;
        font-size: 35px;
        list-style: none;
        color: #888888;
        padding: 7.5px 30px;
        text-align: center;
        -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
        transition: color 0.3s ease;
    }

    a.router-link-active {
        color: #E0E0E0;
    }

    .create-icon {
        font-size: 50px;
        padding: 0px 30px;
        border-left: 0.5px solid #444444;
        border-right: 0.5px solid #444444;
    }
    


</style>