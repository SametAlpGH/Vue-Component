<template>
 <div>
 <button v-bind:id="'BaseDiv_' + propsData.ID">{{propsData.Text }}</button>
</div>
</template>

<script>
export default {
 props: ["propsData"],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>