<template>
    <div class="backdrop" :class="{normal: theme === 'normal'}">
        <div class="modal" :class="{ sale: theme === 'sale'}" >
            <h2>{{header}}</h2>
            <p>{{text}}</p>
            <div>{{count[0]}}</div>
        </div>
    </div>
</template>

<script>
export default ({
    props: ['header', 'text', 'count', 'theme'],
})
</script>

<style scoped>
.modal {
    width: 540px;
    padding: 20px;
    border-radius: 10px;
}

.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
}

.sale {
    background: crimson;
    color: white;
    margin: 100px auto;
}

.sale h2 {
    color: white;
}

.normal {
    top: 30%;
    background: white;
    width: 80%;
    height: 40%;
    display: flex;
    align-items: center;
    justify-content: center;
    left: 10%;
}
</style>