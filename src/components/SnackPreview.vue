<script setup lang="ts">
defineProps<{
    hamburger: {
		bread: string | null,
		salads: string[],
		sauces: string[],
		meat: string | null
	}
}>();

function topBreadType(bread: string | null) 
{
    return bread ? `/images/pao_${bread}_superior.png` : "/images/padrao/pao_superior.png";
}

function bottomBreadType(bread: string | null) 
{
    return bread ? `/images/pao_${bread}_inferior.png` : "/images/padrao/pao_inferior.png";
}

function saladType(salad: string | null) 
{
    return salad ? `/images/${salad}.png` : "/images/padrao/alface.png";
}

function sauceType(sauce: string | null) 
{
    return sauce ? `/images/${sauce}.png` : "/images/padrao/molho.png";
}

function meatType(meat: string | null) 
{
    return meat ? `/images/${meat}.png` : "/images/padrao/hamburguer.png";
}
</script>

<template>
    <div class="col-md-6">
        <div class="row mt-2">
            <div class="col">
                <img :src="topBreadType(hamburger.bread)" alt="Pão topo">
                <img :src="saladType(hamburger.salads[0])" alt="salada">
                <img :src="sauceType(hamburger.sauces[0])" alt="Molho 1">
                <img :src="sauceType(hamburger.sauces[1])" alt="Molho 2">
                <img :src="sauceType(hamburger.sauces[2])" alt="Molho 3">
                <img :src="meatType(hamburger.meat)" alt="Hambúrguer">
                <img :src="bottomBreadType(hamburger.bread)" alt="Pão base">
            </div>
        </div>
    </div>  
</template>
