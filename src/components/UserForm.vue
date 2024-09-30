<script setup lang="ts">
const emit = defineEmits(['userReturned', 'userSubmitted']);
const { user } = defineProps<{
    user: {
        name: string | null,
        address: string | null
    }
}>();

function handleSubmit()
{
    const {
        name,
        address
    } = user;

    if(!name || !address) {
        alert("Informe o nome e o endereço.");
        return;
    }

    emit('userSubmitted');
}
</script>

<template>
    <div class="col-md-6">
        <div class="row mt-2">
            <div class="col">
                <div class="card">
                    <div class="card-header text-uppercase">Informe seus dados</div>
                    
                    <div class="card-body">
                        <div class="mb-3">
                            <label class="form-label">Nome</label>
                            <input type="text" class="form-control" v-model="user.name" />
                        </div>
                        <div class="mb-3">
                            <label class="form-label">Endereço</label>
                            <input type="text" class="form-control" v-model="user.address" />
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="row mt-2">
            <div class="col d-flex justify-content-between">
                <button class="btn btn-warning" @click="emit('userReturned')">Voltar para o lanche</button>
                <button class="btn btn-success" @click.prevent="handleSubmit">Confirmar</button>
            </div>
        </div>
    </div>
</template>
