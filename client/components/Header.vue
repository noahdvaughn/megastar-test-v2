
<template>
    <div class="header" style="background-color: #2a2639;">
        <div class="headerTextFlex">
            <h1 style="margin-left: 1rem;">ToDo's</h1>
            <i class="icon pi pi-ellipsis-h"></i>
        </div>
        <div class="header-button-flex">
            <div :class="{'header-button-underlined' : viewingOpen}" class="header-button" @click="$emit('setViewingOpen', true)">
                <h3>Open</h3>
            </div>
            <div :class="{'header-button-underlined' : !viewingOpen}" class="header-button" @click="$emit('setViewingOpen', false)">
                <h3 >Closed</h3>
            </div>
    

        </div>
    </div>
</template>

    <script>
    
    import 'primeicons/primeicons.css';
    
    export default {     
        setup(){        
        },       
        props: {
            viewingOpen: Boolean
        },
        
        methods: {
            
        }
    }
    
    </script>


<style>
.header{
    width: 100vw;
}
h1{
    color: white
}
h3{
    color: white;
}
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