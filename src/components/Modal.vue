<template>
    <div class="backdrop" @click.self="closeModal"> 
        <div class="modal" :class="{ sale: theme === 'sale', normal: theme === 'normal'}" >
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
    padding: 40px;
    border-radius: 10px;
    margin: auto;
    margin-top: 100px;
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
}

.sale h2 {
    color: white;
}

.normal {
    background: rgb(37, 4, 65);
    color: rgb(216, 238, 252);
}

</style>