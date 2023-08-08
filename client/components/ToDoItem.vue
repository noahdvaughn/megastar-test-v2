<template >
    <div>
        <div>
            <!-- <i v-if="item.completed === false" class="icon pi pi-circle-fill"></i>
            <i v-if="item.completed === false" class="icon pi pi-circle-fill"></i> -->
            <v-icon>mdi-email</v-icon>

        </div>
        <h1>{{ item.title }}</h1>
        <h1>{{ item.completed }}</h1>
        <h1>{{ item.userId }}</h1>
        
    </div>
</template>

<script>
import 'primeicons/primeicons.css';

export default {
    data: () => ({
    
    }),
    props: {
        data: Array,
        item: Object
    }    
}
</script>

<style >
    
</style>