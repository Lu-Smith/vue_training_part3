<template>
    <div class="backdrop" :class="{normal: theme === 'normal'}" @click.self="closeModal"> 
        <div class="modal" :class="{ sale: theme === 'sale'}" >
            <slot>default content</slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default ({
    props: ['theme'],
    methods: {
        closeModal() {
            this.$emit('close')
        }
    }
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
    margin: 300px auto;
}

.sale h2 {
    color: white;
}

.normal {
    top: 50%;
    background: white;
    width: 80%;
    height: 40%;
    display: flex;
    align-items: center;
    justify-content: center;
    left: 10%;
}
</style>