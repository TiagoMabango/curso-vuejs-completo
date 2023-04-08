<template>

    <div id="usuario">
        <h2>Olá: {{nome}}</h2>
    </div>

</template>

<script>

export default {
     name: 'Usuario',
     props: {
        nome: {
            type:String,
            required: true
        }
     }
}
</script>

<style>
  h2{
    color: red;
  }
</style>