<template>
    <div class="footer">
        <p>Feel free to check out our social media channels</p>
        <div class="social-icons">
            <a href="https://www.facebook.com" target="_blank">
                <i class="pi pi-facebook" style="font-size: 1.5rem"></i>
            </a>
            <a href="https://www.instagram.com" target="_blank">
                <i class="pi pi-instagram" style="font-size: 1.5rem"></i>
            </a>
            <a href="https://www.linkedin.com" target="_blank">
                <i class="pi pi-linkedin" style="font-size: 1.5rem"></i>
            </a>
            <a href="https://www.linkedin.com" target="_blank">
                <i class="pi pi-tiktok" style="font-size: 1.5rem"></i>
            </a>
        </div>
    </div>
</template>
    
<script>
export default {
    name: 'Footer'
}
</script>
    
<style scoped>
.footer {
    color: #000000;
    padding: 1rem;
    text-align: center;
    margin-top: 100px;
}

.social-icons {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin-top: 10px;
}
i{
    color: rgb(0, 0, 0);
}
i:hover{
    color: #475f53;
}
</style>