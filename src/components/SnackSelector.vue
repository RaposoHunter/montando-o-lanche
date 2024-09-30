<script setup lang="ts">
import SnackInput from "./SnackInput.vue";

const emit = defineEmits(["snackSelected"]);
let { step, hamburger } = defineProps<{
    step: number,
    hamburger: {
		bread: string | null,
		salads: string[],
		sauces: string[],
		meat: string | null
	}
}>();

function handleSubmit()
{
    const {
        bread,
        meat
    } = hamburger;

    if(!bread || !meat) {
        alert("Selecione o tipo do pão e o tipo de hambúrguer pelo menos.");
        return;
    }

    emit('snackSelected');
}
</script>

<template>
    <div class="col-md-6 mt-2 d-flex flex-column gap-2">
        <SnackInput title="Tipo do Pão">
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="radio" v-model="hamburger.bread" value="gergelim">
                <label class="form-check-label">Gergelim</label>
            </div>
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="radio" v-model="hamburger.bread" value="australiano">
                <label class="form-check-label">Australiano</label>
            </div>
        </SnackInput>

        <SnackInput title="Saladas">
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="checkbox" v-model="hamburger.salads" value="alface">
                <label class="form-check-label">Alface</label>
            </div>
        </SnackInput>

        <SnackInput title="Molhos">
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="checkbox" v-model="hamburger.sauces" value="ketchup">
                <label class="form-check-label">Ketchup</label>
            </div>
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="checkbox" v-model="hamburger.sauces" value="mostarda">
                <label class="form-check-label">Mostarda</label>
            </div>
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="checkbox" v-model="hamburger.sauces" value="maionese">
                <label class="form-check-label">Maionese</label>
            </div>
        </SnackInput>

        <SnackInput title="Tipos de Hambúrguer">
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="radio" v-model="hamburger.meat" value="bovino">
                <label class="form-check-label">Bovino</label>
            </div>
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="radio" v-model="hamburger.meat" value="frango">
                <label class="form-check-label">Frango</label>
            </div>
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="radio" v-model="hamburger.meat" value="soja">
                <label class="form-check-label">Soja</label>
            </div>
        </SnackInput>

        <div class="row mt-2">
            <div class="col d-flex justify-content-end">
                <button type="button" class="btn btn-primary" @click.prevent="handleSubmit">Fazer pedido</button>
            </div>
        </div>
    </div>
</template>
