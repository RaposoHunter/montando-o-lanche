<script setup lang="ts">
import SnackInput from "./SnackInput.vue";

defineProps<{
    hamburger: {
		bread: string | null,
		salads: string[],
		sauces: string[],
		meat: string | null
	}
}>();

</script>

<template>
    <div class="col-md-6 mt-2 d-flex flex-column gap-2">
        <SnackInput title="TIPO DO PÃO">
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="radio" v-model="hamburger.bread" value="gergelim">
                <label class="form-check-label">Gergelim</label>
            </div>
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="radio" v-model="hamburger.bread" value="australiano">
                <label class="form-check-label">Australiano</label>
            </div>
        </SnackInput>

        <SnackInput title="SALADAS">
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="checkbox" v-model="hamburger.salads" value="alface">
                <label class="form-check-label">Alface</label>
            </div>
        </SnackInput>

        <SnackInput title="MOLHOS">
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

        <SnackInput title="TIPOS DE HAMBÚRGUER">
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
    </div>
</template>
