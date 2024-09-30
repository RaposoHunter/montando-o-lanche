<script setup lang="ts">
const emit = defineEmits(['repeatOrder', 'newOrder']);

setTimeout(() => {
    emit('newOrder');
}, 7000);
</script>

<template>
    <div class="col-md-6">
        <div class="row mt-2">
            <div class="col">
                <div class="card">
                    <div class="card-header text-uppercase">Pedido confirmado</div>
                    
                    <div class="card-body">
                        <p>Agora é só aguardar 10 minutinhos!</p>
                        <p>Vamos chamar vc em breve ;&rpar;</p>
                    </div>
                </div>
            </div>
        </div>
        <div class="row mt-2">
            <div class="col d-flex justify-content-between">
                <button class="btn btn-primary" @click="emit('repeatOrder')">Repetir pedido</button>
                <button class="btn btn-success" @click="emit('newOrder')">Novo pedido</button>
            </div>
        </div>
    </div>
</template>
