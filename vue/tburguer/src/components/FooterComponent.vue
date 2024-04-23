<template>
    <div>
        <footer id="footer">
            <p>Construido por Felipe Pereira do Nascimento &copy;</p>
        </footer>
    </div>
</template>

<script>
    export default {
        name: "FooterComponent"
    }
</script>

<style scoped>
    #footer{
        height: 80px;
        background-color: #333;
        color: goldenrod;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    #footer p{
        font-size: 14px;
    }
</style>