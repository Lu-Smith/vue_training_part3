<template>
    <div class="backdrop">
        <div class="modal">
            <h2>Modal Title</h2>
            <p>modal content</p>
        </div>
    </div>
</template>
<style scoped>
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: #fff;
    border-radius: 10px;
}

.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
}

h2 {
    color: rgb(89, 156, 156);
    font-size: 30px;
}
</style>