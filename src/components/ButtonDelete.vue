<template>
    <button>
        <button @click="$emit('onClick')">

            <!-- fungsi slot ini agar dynamic (bisa diakses oleh semua) -->
            <slot/> 
        </button>
    </button>
</template>