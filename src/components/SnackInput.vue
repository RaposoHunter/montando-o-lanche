
<script setup lang="ts">
defineProps<{ title: string }>();
</script>

<template>
    <div class="row">
        <div class="col">
            <div class="card">
                <div class="card-header">{{ title }}</div>
                <div class="card-body">
                    <slot />
                </div>
            </div>
        </div>
    </div>
</template>
