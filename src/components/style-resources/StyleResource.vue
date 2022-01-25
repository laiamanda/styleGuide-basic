<template>
    <li>
        <base-card>
            <header>
                <h3> {{ title }} </h3>
                <base-button mode="flat" @click="deleteResource(id)"> Delete </base-button>   
            </header>
            <p> {{ description }}</p>
            <a :href = "link">View Resource</a>
        </base-card>
    </li>
</template>

<script>
export default{
    props: ['id', 'title', 'description', 'link'],
    inject: ['deleteResource'],
}
</script>

<style scoped>
li {
  margin: auto;
  max-width: 40rem;
}
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
h3 {
  font-size: 1.75rem;
  margin: 0.5rem 0;
}
p {
  margin: 0.5rem 0;
}
a {
  text-decoration: none;
  color: #109648;
}

a:hover,
a:active {
  color: #0b7236;
}
</style>