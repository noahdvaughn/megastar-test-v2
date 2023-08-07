<script>
import 'primeicons/primeicons.css';
import {reactive} from 'vue'

export default {
    // const viewingOpen = reactive(true)
    data: () => ({
        viewingOpen: true
    })

   
}

</script>

<template>
    <div class="header">
        <div class="headerTextFlex">
            <h1 style="margin-left: 1rem;">ToDos</h1>
            <i class="icon pi pi-ellipsis-h"></i>
        </div>
        <div class="header-button-flex">
            <div :class="{'header-button-underlined' : viewingOpen}" class="header-button">
                <h3>Open</h3>
            </div>
            <div :class="{'header-button-underlined' : !viewingOpen}" class="header-button">
                <h3 >Closed</h3>
            </div>

        </div>
    </div>
</template>


<style>
.headerTextFlex{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.header-button-flex{
    display: flex;
    justify-content: space-around;
    align-items: center;
}
.icon{
    color: white;
    font-size: 3rem;
    margin-right: 1.5rem;
}
.header-button{
    cursor: pointer;
   
    border-bottom: 5px solid transparent;
    &:hover{
        border-bottom: 5px solid white;
    }
}
.header-button-underlined{
    border-bottom: 5px solid white;
}

</style>