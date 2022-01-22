<template>
    <ul>
        <style-resource
            v-for= "res in resources"
            :key = "res.id"
            :id = "res.id"
            :title = "res.title"
            :description = "res.description"
            :link = "res.link" 
        >
        </style-resource>
    </ul>
</template>

<script>
import StyleResource from "./StyleResource.vue";

export default{
    inject: ['resources'],
    components: {
        StyleResource
    }
}
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>