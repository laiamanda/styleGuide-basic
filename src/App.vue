<template>
   <the-header title = "stylesGuide"></the-header>
   <the-resources></the-resources>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import TheResources from './components/style-resources/TheResources.vue';
export default{
    components:{
        TheHeader,
        TheResources,
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@300;400;700;900&display=swap');

*{
    box-sizing: border-box;
}
html {
    font-family: 'Raleway', sans-serif;
}
body{
    margin: 0;
}

</style>
