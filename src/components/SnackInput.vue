
<script setup lang="ts">
defineProps<{ title: string }>();
</script>

<template>
    <div class="row">
        <div class="col">
            <div class="card">
                <div class="card-header text-uppercase">{{ title }}</div>
                <div class="card-body">
                    <slot />
                </div>
            </div>
        </div>
    </div>
</template>
