<!-- Card component provides a styled container using slots for flexible content -->
<div class="card">
    <slot></slot>
</div>

<style>
    .card{
        background-color: #fff;
        padding: 40px 50px;
        position: relative;
        border-radius: 15px;
        margin: 20px 0;
        color: #333;
    }
</style>