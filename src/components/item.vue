<template>
  <div>{{names}}
    <button v-on:click="info(names)">Info</button>
  </div>
</template>

<script>
export default {
    name: 'item',
    props: ['names'],
    methods:{
        info(names){
            alert(names)
        }
    }
}
</script>
