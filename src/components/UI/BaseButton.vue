<template>
    <button :class ="mode">
        <slot></slot>
    </button>
</template>

<script>
export default{
    props: ['mode']
}
</script>

<style scoped>
button{
  padding: 0.75rem 1.5rem;
  font-family: in<template>
    <button :class ="mode">
        <slot></slot>
    </button>
</template>

<script>
export default{
    props: ['mode']
}
</script>

<style scoped>
button{
  padding: 0.75rem 1.5rem;
  font-family: inherit;
  background-color: #18A999;
  border: 1px solid #18A999;
  color: white;
  cursor: pointer;
}

button:hover,
button:active {
  background-color: #1a9486;
  border-color: #1a9486;
}

.flat {
  background-color: transparent;
  color: #F51507;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #ffefef;
}
</style>
herit;
  background-color: #18A999;
  border: 1px solid #18A999;
  color: white;
  cursor: pointer;
}

button:hover,
button:active {
  background-color: #1a9486;
  border-color: #1a9486;
}

.flat {
  background-color: transparent;
  color: #F51507;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #ffefef;
}
</style>
